---
name: openstoryline
description: "Install, run and drive FireRed-OpenStoryline — a self-hosted AI video-editing agent (clip splitting, media search, script, TTS voiceover, subtitles, render) — on the user's own computer. Use when the user asks to set up, start, or edit a video with OpenStoryline. Requires a local machine with Python 3.11, ffmpeg, multi-GB model/resource download and LLM+VLM API keys."
---

# OpenStoryline — התקנה, הפעלה ועריכה

מאגר: https://github.com/FireRedTeam/FireRed-OpenStoryline. זו **אפליקציה** (שני שרתים מקומיים: MCP + Web), לא סקיל עצמאי. הכל רץ על המחשב של המשתמש (device_bash / טרמינל), לא בענן.

## דרישות מוקדמות — אמור למשתמש מראש

- git, Python **≥ 3.11**, ffmpeg, wget, unzip.
- הורדה גדולה (מודלים + משאבים, כמה GB) דרך `download.sh`.
- מפתחות API חובה: `llm.model/base_url/api_key` וגם `vlm.model/base_url/api_key` (מודל עם ראייה). אופציונלי: Pexels לחיפוש מדיה, ספק TTS אחד (minimax / bytedance / 302).
- מעברי AI (AI transitions) יקרים — לא להפעיל כברירת מחדל.

## התקנה (פעם אחת)

```bash
git clone https://github.com/FireRedTeam/FireRed-OpenStoryline && cd FireRed-OpenStoryline
python3 -m venv .venv && .venv/bin/python -m pip install --upgrade pip
.venv/bin/python -m pip install -r requirements.txt
bash download.sh            # ארוך; wget ממשיך אחרי ניתוק
```
הגדרת config.toml (בקש מהמשתמש את הערכים, אל תמציא):
```bash
.venv/bin/python scripts/update_config.py --config ./config.toml --set llm.model=...
.venv/bin/python scripts/update_config.py --config ./config.toml --set llm.base_url=...
.venv/bin/python scripts/update_config.py --config ./config.toml --set llm.api_key=...
.venv/bin/python scripts/update_config.py --config ./config.toml --set vlm.model=...
.venv/bin/python scripts/update_config.py --config ./config.toml --set vlm.base_url=...
.venv/bin/python scripts/update_config.py --config ./config.toml --set vlm.api_key=...
```
אימות לפני שמכריזים "מותקן":
```bash
.venv/bin/pip check
PYTHONPATH=src .venv/bin/python -c "from open_storyline.config import load_settings; load_settings('config.toml'); print('config_ok')"
test -f .storyline/models/transnetv2-pytorch-weights.pth && test -d resource/bgms && echo resources_ok
```
אל תגיד "ההתקנה הושלמה" אם רק חבילות הפייתון הותקנו והמשאבים עוד לא ירדו.

## הפעלה (שני תהליכים ארוכי-חיים, בשני shells)

```bash
PYTHONPATH=src .venv/bin/python -m open_storyline.mcp.server          # → Uvicorn running on http://127.0.0.1:8001 (עולה כמה דקות)
PYTHONPATH=src .venv/bin/python -m uvicorn agent_fastapi:app --host 127.0.0.1 --port 8005
```
כללים: להאזין רק ל-127.0.0.1; לא לעטוף ב-`| head`/`timeout`/`pkill`; לא להרוג את השרתים באמצע משימה; פורט תפוס → החלף פורט (`local_mcp_server.port`).

## עריכה

1. `curl -s -X POST http://127.0.0.1:8005/api/sessions` → שמור את ה-`session_id` (כל ההמשך תלוי בו).
2. העלאת חומרים: `curl -s -X POST http://127.0.0.1:8005/api/sessions/{session_id}/media -F "files=@/path/input.mp4"`, או לקבצים גדולים `cp` ל-`outputs/{session_id}/media`.
3. שיחה עם הסוכן דרך סקריפט הגשר של הסקיל המקורי (משוך אותו מהמאגר: `.claude/skills/openstoryline-use/scripts/bridge_openstoryline.py`):
   `python bridge_openstoryline.py --base-url http://127.0.0.1:8005 --session-id <id> --prompt "<בקשת העריכה>" --lang en`
   (`--lang` תומך רק ב-zh/en — בקשות בעברית עובדות, ה-UI/כתוביות ב-en.)
4. התקדמות רואים בלוג של שרת ה-Web: `filter_clips → group_clips → generate_script → generate_voiceover → render_video`. אם הגשר עדיין מחכה אבל הלוג מתקדם — ממתינים, לא מאתחלים.
5. תוצר: `find .storyline/.server_cache/<session_id> -name "output_*.mp4"`. עריכה חוזרת — אותו `session_id`, פרומפט חדש → `output_*.mp4` חדש.
6. בסיום תמיד להחזיר למשתמש: `session_id`, נתיב ה-mp4 המלא, והאם נוצר קובץ חדש.

## פירוט מלא

הסקילים המקוריים (עם פתרון תקלות ו-Windows): משוך `https://raw.githubusercontent.com/FireRedTeam/FireRed-OpenStoryline/main/.claude/skills/openstoryline-install/SKILL.md` ו-`.../openstoryline-use/SKILL.md`.