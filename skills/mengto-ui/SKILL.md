---
name: mengto-ui
description: "Use as a quality gate whenever creating, reviewing or prompting for UI: prevent and audit generic AI design slop, and write design-first UI prompts. Index of 3 MengTo UI skills fetched on demand."
---

# MengTo ui skills — index + fetch on demand

מאגר: https://github.com/MengTo/Skills (תיקייה `agent-skills/ui/`). הסקילים עצמם לא מוטמעים כאן — מושכים אותם מהמאגר בזמן העבודה, כך שהם תמיד מעודכנים.

## איך להשתמש

1. מצא ברשימה למטה את הסקיל (או 2–3 סקילים) שהכי מתאים למשימה. `no-ai-design-slop` הוא שער איכות פסיבי — טען אותו בכל עבודת UI, גם בלי בקשה מפורשת.
2. משוך את ה-SKILL.md המלא:
   `WebFetch("https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/ui/<slug>/SKILL.md", "Return the full file verbatim")`
   (אם WebFetch מקצר — בקש חלקים: "Return lines 1-200 verbatim", וכו'.)
3. אם ה-SKILL.md מפנה לקבצים יחסיים (`references/…`, `agents/…`, `assets/…`, `scripts/…`) — משוך אותם מאותה תיקייה:
   `https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/ui/<slug>/<relative-path>`
   קבצים בינאריים (תמונות/mp4) אי אפשר למשוך — דלג עליהם.
4. עקוב אחרי ההוראות בסקיל שנמשך במלואן. הן גוברות על ברירות מחדל שלך.
5. אם המשיכה נכשלת — אמור למשתמש, ואל תמציא את תוכן הסקיל.

## הרשימה (3)

- **audit-ai-design-slop** (+agents/) — Audit websites, apps, screenshots, mockups, and design code for harmful AI-design clichés, generic generated defaults, and established UI defects. Use when the user wants evidence-backed design feedback, an anti-slop review, or a removal-first cleanup plan without a speculative redesign.
- **design-first-ui-prompting** — Use when you need design-first, spec-driven, skimmable prompts for UI generation. Covers prompt structure, constraints, variations, typography/spacing rules, and iteration workflow for consistent UI outputs.
- **no-ai-design-slop** (+agents/) — Prevent and remove generic AI-generated design defaults, incoherent visual choices, and established UI defects while creating, revising, or reviewing websites, apps, screenshots, mockups, and design code. Use as a passive quality gate during UI work or for an explicit anti-slop cleanup; preserve the chosen art direction instead of forcing a neutral redesign.