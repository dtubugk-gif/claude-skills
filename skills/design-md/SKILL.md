---
name: design-md
description: "Use when the user wants a UI, page or app styled like a known brand (\"make it look like Stripe / Linear / Apple / Notion…\"), or asks for a DESIGN.md / design language / design tokens of a real product. Fetches the matching DESIGN.md from VoltAgent/awesome-design-md (74 brands) and builds to it."
---

# DESIGN.md לפי מותג

מאגר: https://github.com/VoltAgent/awesome-design-md — 74 קבצי DESIGN.md (פורמט Google Stitch) שמתארים שפת עיצוב של מוצר אמיתי: צבעים, טיפוגרפיה, רדיוסים, צללים, מרווחים, רכיבים וכללי "אל תעשה". כל קובץ ~20–30KB.

## איך להשתמש

1. זהה את המותג מבקשת המשתמש ומצא את ה-slug ברשימה למטה. אם המותג לא ברשימה — אמור זאת והצע את הקרוב ביותר (למשל "כמו Vercel" → `vercel`; "פינטק כהה" → `revolut` / `wise` / `stripe`).
2. משוך את הקובץ:
   `WebFetch("https://raw.githubusercontent.com/VoltAgent/awesome-design-md/main/design-md/<slug>/DESIGN.md", "Return the full file verbatim, including all YAML tokens")`
   אם התוצאה מקוצרת — משוך בחלקים ("Return the colors and typography sections verbatim", "Return the components and rules sections verbatim").
3. בנה לפי הטוקנים **בדיוק** — hex, פונטים (עם fallback), רדיוסים, צללים, מרווחים. אל תחליף בברירות מחדל שלך. אם הפרויקט הוא קובץ HTML בודד — הכנס את הטוקנים כ-CSS custom properties ב-`:root` ובנה משם.
4. אם המשתמש עובד בפרויקט עם תיקייה — הצע לשמור את הקובץ כ-`DESIGN.md` בשורש הפרויקט, כדי שכל סוכן ימשיך לעבוד לפיו.
5. זה **השראה** משפת עיצוב, לא העתקה: אל תשתמש בלוגו, בשם המותג או בנכסים ממותגים בתוצר, אלא אם זה הפרויקט של המשתמש עצמו.
6. משיכה נכשלה → אמור למשתמש; אל תמציא טוקנים בשם המותג.

## slugs זמינים (74)

airbnb, airtable, apple, binance, bmw, bmw-m, bugatti, cal, claude, clay, clickhouse, cohere, coinbase, composio, cursor, dell-1996, elevenlabs, expo, ferrari, figma, framer, hashicorp, hp, ibm, intercom, kraken, lamborghini, linear.app, lovable, mastercard, meta, minimax, mintlify, miro, mistral.ai, mongodb, nike, nintendo-2001, notion, nvidia, ollama, opencode.ai, pinterest, playstation, posthog, raycast, renault, replicate, resend, revolut, runwayml, sanity, sentry, shopify, slack, spacex, spotify, starbucks, stripe, supabase, superhuman, tesla, theverge, together.ai, uber, vercel, vodafone, voltagent, warp, webflow, wired, wise, x.ai, zapier

## קיצורי דרך לפי אופי

- SaaS/דבלופר, נקי ובהיר: stripe, linear.app, vercel, notion, resend, cal, supabase
- כהה-טכני/פרימיום: raycast, warp, cursor, posthog, sentry, x.ai
- AI/מודלים: claude, mistral.ai, cohere, elevenlabs, runwayml, together.ai, replicate
- צרכני/מותגי: apple, nike, airbnb, spotify, starbucks, uber, pinterest
- רכב/יוקרה: tesla, ferrari, lamborghini, bugatti, bmw-m, renault
- פינטק: revolut, wise, coinbase, kraken, binance, mastercard
- רטרו: nintendo-2001, dell-1996