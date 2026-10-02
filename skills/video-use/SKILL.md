---
name: video-use
description: "Edit real video footage by conversation — transcribe, cut talking heads/montages/tutorials, color grade, overlay animations, burn subtitles — and make Manim (3Blue1Brown-style) math/technical explainer animations. Use when the user has video files to edit, or asks for an animated explainer. Fetches browser-use/video-use at run time."
---

# video-use — עריכת וידאו בשיחה (+ manim-video)

מאגר: https://github.com/browser-use/video-use. הסקיל מסתמך על סקריפטי עזר (`helpers/*.py`) ועל ffmpeg, ולכן **לא מוטמע כאן** — מושכים את המאגר בתחילת כל משימה.

## דרישות (בדוק לפני שמתחילים)

- `ffmpeg` + `ffprobe` ב-PATH (`which ffmpeg`). אין → התקן (`apt-get install -y ffmpeg` / `brew install ffmpeg`).
- Python 3 + `pip install requests librosa matplotlib pillow numpy --break-system-packages`.
- **מפתח ElevenLabs** (`ELEVENLABS_API_KEY`) — חובה לתמלול (Scribe). בלעדיו אין חיתוך לפי דיבור; אפשר עדיין לחתוך לפי זמנים, לצבוע, לשכב אנימציות. אם אין מפתח — אמור למשתמש בשורה אחת ובקש, או המשך בלי תמלול.
- קבצי הווידאו חייבים להיות נגישים לשלל (בסביבת ענן: המשתמש מעלה אותם לצ'אט או מחבר תיקייה; בהיקף גדול עדיף להריץ על המחשב שלו דרך device_bash).

## הפעלה

1. שכפל (פעם אחת לסשן) לתיקיית סקראצ':
   ```bash
   test -d "$SCRATCH/video-use" || git clone -q --depth 1 https://github.com/browser-use/video-use "$SCRATCH/video-use"
   ```
   (`$SCRATCH` = תיקיית הסקראצ' של הסשן; לא `/tmp` של המשתמש.)
2. קרא במלואו `"$SCRATCH/video-use/SKILL.md"` ועקוב אחריו. זה הסקיל האמיתי — כללי ה-production (fps, orientation, audio-first, ask → confirm → execute → iterate → persist) הם קשיחים.
3. קרא את `helpers/` לפני שימוש: `transcribe.py`, `transcribe_batch.py`, `pack_transcripts.py`, `timeline_view.py`, `grade.py`, `render.py`. מריצים כ-`python helpers/<name>.py` מתוך שורש המאגר, עם `.env` שמכיל `ELEVENLABS_API_KEY=...` (או משתנה סביבה).
4. **אנימציות מתמטיות/טכניות** (3Blue1Brown, אלגוריתמים, נוסחאות, דיאגרמות ארכיטקטורה): קרא `"$SCRATCH/video-use/skills/manim-video/SKILL.md"` ואת `references/` שלו לפי הצורך; `scripts/setup.sh` מתקין Manim CE.
5. אל תיגע בחיתוך לפני שהמשתמש אישר את התוכנית במילים פשוטות (זה כלל של הסקיל, לא נימוס).
6. תוצר סופי: mp4 מרונדר + מסירה למשתמש. אם השכפול נכשל — אמור למשתמש; אל תמציא את ה-helpers.

## מה זה כן ומה זה לא

- כן: פוטאז' אמיתי (talking head, מונטאז', מדריך, ראיון, טיול), תמלול, חיתוך לפי דיבור/שקט, grade, כתוביות, overlays, ו-manim.
- לא: motion graphics מאפס ב-React — לזה יש את הסקיל `remotion-motion-graphics`. אפשר לשלב: video-use לחיתוך, remotion לאינטרו/אאוטרו/כותרות.