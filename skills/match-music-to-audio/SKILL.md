---
name: "match-music-to-audio"
description: "Fit a music track to a voice/audio file: loop or trim it to length, balance loudness, auto-duck under speech, fades, and export the mix (ffmpeg)."
---

# התאמת מוזיקה לקובץ אודיו

מטרה: לקחת קובץ אודיו ראשי (קריינות / דיבור / פודקאסט / פס קול של סרטון) וקובץ מוזיקה, ולהוציא מיקס אחד שבו המוזיקה באורך הנכון, בעוצמה הנכונה, יורדת אוטומטית כשמדברים, ונכנסת/יוצאת בפייד.

## 0. להבין מה המשתמש רוצה (אם לא ברור)
- **מוזיקת רקע מתחת לדיבור** (ברירת מחדל) → כל הצעדים למטה.
- **רק להשוות אורך** (בלי דאקינג) → דלג על שלב 4.
- **להתאים טמפו/BPM** בין שני קטעים מוזיקליים → שלב 6.
- להחזיר את הקובץ בפורמט של המקור אם לא צוין אחרת (MP3 192k / WAV / M4A).

## 1. בדיקת הקבצים
```bash
ffprobe -v error -show_entries format=duration:stream=sample_rate,channels -of default=nw=1 voice.xxx
ffprobe -v error -show_entries format=duration:stream=sample_rate,channels -of default=nw=1 music.xxx
# עוצמה נוכחית:
ffmpeg -i voice.xxx -af loudnorm=print_format=summary -f null - 2>&1 | tail -12
```
שמור: `VD` = אורך הקול, `MD` = אורך המוזיקה.

## 2. אורך
- אורך יעד = `VD + tail` (tail = 2–4 שניות אחרי שהדיבור נגמר, שהמוזיקה תסגור בנעימות). אפשר גם intro של 1–3 שניות לפני הדיבור עם `adelay` על הקול.
- אם `MD < אורך יעד` → לולאה: הוסף `-stream_loop -1` לפני `-i music` (ואז `atrim` חותך).
  - מקצועית: לולאה חדה נשמעת. עדיף לחתוך בנקודת תיבה/ביט (ראה שלב 6 לזיהוי ביטים) או לעשות crossfade: `acrossfade=d=2` בין שני עותקים.
- אם `MD > אורך יעד` → `atrim=0:TARGET` + fade-out.

## 3. עוצמות (הכי חשוב)
- נרמל את הקול ל-**-16 LUFS** (פודקאסט/רשתות), true peak -1.5 dBTP. לשידור/EBU R128: -23 LUFS.
- נרמל את המוזיקה לאותה נקודה ואז הורד **18–22 dB** (מוזיקה עם ווקאל/סינתים בולטים → 22–25 dB). התוצאה: מוזיקה ב־~‎-34 עד ‎-38 LUFS מתחת לדיבור.
- **מלכודת:** `loudnorm` מוציא 192kHz → תמיד `aresample=48000` מיד אחריו.

## 4. דאקינג אוטומטי (sidechain)
המוזיקה נדחסת רק כשיש דיבור:
`[music][voice_sc]sidechaincompress=threshold=0.02:ratio=8:attack=20:release=400`
- `release` 300–600ms = חזרה טבעית בין משפטים. ratio 6–10.
- **מלכודת:** sidechaincompress נגמר כשהקלט הקצר נגמר → לרפד את הקול עם `apad=pad_dur=TAIL` לפני ה-`asplit`.

## 5. הפקודה המלאה (נבדקה)
```bash
VOICE=voice.mp3; MUSIC=music.mp3; OUT=mix.mp3
VD=$(ffprobe -v error -show_entries format=duration -of csv=p=0 "$VOICE")
TAIL=3; TARGET=$(python3 -c "print($VD+$TAIL)"); FO=$(python3 -c "print($VD+$TAIL-2.5)")
ffmpeg -y -i "$VOICE" -stream_loop -1 -i "$MUSIC" -filter_complex "\
[0:a]loudnorm=I=-16:TP=-1.5:LRA=11,aresample=48000,aformat=channel_layouts=stereo,apad=pad_dur=$TAIL,asplit=2[v][sc];\
[1:a]loudnorm=I=-16:TP=-1.5,aresample=48000,aformat=channel_layouts=stereo,volume=-18dB,atrim=0:$TARGET,asetpts=N/SR/TB,afade=t=in:d=1.5,afade=t=out:st=$FO:d=2.5[m];\
[m][sc]sidechaincompress=threshold=0.02:ratio=8:attack=20:release=400[md];\
[v][md]amix=inputs=2:duration=longest:normalize=0,alimiter=limit=0.89[out]" \
-map "[out]" -c:a libmp3lame -b:a 192k "$OUT"
```
- `normalize=0` ב-amix חובה — אחרת amix מחליש כל ערוץ ומשבש את היחסים.
- לסרטון: `-i video.mp4` כקלט נוסף, `-map 0:v -c:v copy -map "[out]" -c:a aac -b:a 192k -shortest`.

## 6. התאמת טמפו (רק אם ביקשו)
```python
import librosa
y, sr = librosa.load('music.mp3')
tempo, beats = librosa.beat.beat_track(y=y, sr=sr)
beat_times = librosa.frames_to_time(beats, sr=sr)  # נקודות חיתוך/לולאה נקיות
```
- שינוי מהירות בלי לשנות גובה: `atempo=RATIO` (0.5–2.0; לשרשר אם מעבר), או `rubberband=tempo=RATIO` אם זמין (איכות טובה יותר).
- מעבר ±8% בטמפו נשמע מלאכותי — להגיד למשתמש ולהציע לחתוך/ללפלף במקום למתוח.

## 7. אימות לפני מסירה
- `ffprobe` על הפלט: אורך = TARGET (±0.1s).
- `loudnorm=print_format=summary` על הפלט: Integrated ≈ -16 LUFS, True peak ≤ -1 dBTP.
- בדיקת דאקינג: `astats` על קטע עם דיבור מול קטע בלי — המוזיקה צריכה להיות נמוכה בבירור בקטעי הדיבור.
- אם אפשר, להשמיע/להציע האזנה ל-10 השניות הראשונות ולסוף.

## דעה מקצועית לומר למשתמש (פעם אחת)
- מוזיקה עם שירה מתחת לדיבור פוגעת בהבנה — להמליץ על אינסטרומנטלי.
- זכויות יוצרים: לפרסום ציבורי להשתמש במוזיקה ברישיון/ללא תמלוגים.