---
name: mengto-3d
description: "Use for 3D scene rendering quality in Three.js: sky, sun rays, falling leaves, seasons, high-poly models, PBR textures, Retina/HiDPI rendering, virtual tours. Index of 8 MengTo 3D skills fetched on demand."
---

# MengTo 3d skills — index + fetch on demand

מאגר: https://github.com/MengTo/Skills (תיקייה `agent-skills/3d/`). הסקילים עצמם לא מוטמעים כאן — מושכים אותם מהמאגר בזמן העבודה, כך שהם תמיד מעודכנים.

## איך להשתמש

1. מצא ברשימה למטה את הסקיל (או 2–3 סקילים) שהכי מתאים למשימה. אם המשתמש ביקש אפקט/סגנון ספציפי, העדף את הסקיל הצר ביותר שמכסה אותו.
2. משוך את ה-SKILL.md המלא:
   `WebFetch("https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/3d/<slug>/SKILL.md", "Return the full file verbatim")`
   (אם WebFetch מקצר — בקש חלקים: "Return lines 1-200 verbatim", וכו'.)
3. אם ה-SKILL.md מפנה לקבצים יחסיים (`references/…`, `agents/…`, `assets/…`, `scripts/…`) — משוך אותם מאותה תיקייה:
   `https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/3d/<slug>/<relative-path>`
   קבצים בינאריים (תמונות/mp4) אי אפשר למשוך — דלג עליהם.
4. עקוב אחרי ההוראות בסקיל שנמשך במלואן. הן גוברות על ברירות מחדל שלך.
5. אם המשיכה נכשלת — אמור למשתמש, ואל תמציא את תוכן הסקיל.

## הרשימה (8)

- **3d-falling-leaves** (+agents/) — Build recognizable falling leaves in world space using instanced geometry, independent tumble, coupled sideways drift, shared wind, scene occlusion, and camera-aware recycling. Use for 3D autumn leaves or drifting foliage in Three.js and similar scenes; use falling-leaves (web-design) for a 2D canvas overlay.
- **3d-four-seasons** (+agents/) — Add coordinated spring, summer, fall, and winter states to a 3D scene, blending foliage, sunlight, sky, ground materials, snow, and particles without rebuilding the world. Use for seasonal controls, architectural walkthroughs, and outdoor scenes with four-season transitions.
- **3d-high-poly-models** (+agents/) — Create or integrate highly detailed 3D models with smooth silhouettes, shaped surfaces, believable bevels, and close-up geometry, then prepare suitable runtime LODs and loading. Use when a user requests high polygon counts, ultra-realistic models, detailed architectural assets, or removal of visibly faceted geometry.
- **3d-high-resolution-textures** (+agents/) — Build sharp, physically coherent high-resolution materials for 3D rendering with appropriate PBR maps, texel density, UV direction, mipmaps, anisotropic filtering, and progressive asset delivery. Use for detailed wood, stone, fabric, foliage, and architectural close-ups without excessive download or GPU memory costs.
- **3d-retina-resolution** (+agents/) — Render a 3D canvas sharply on Retina and HiDPI displays, including explicit 200 percent resolution, synchronized renderer and post-processing sizes, correct pointer coordinates, and measured quality fallbacks. Use for blurry WebGL output, 2x rendering, high-resolution previews, and display-density changes.
- **3d-sky-background** (+agents/) — Create a camera-correct sky background for a 3D scene with a procedural atmosphere or panorama, horizon haze, aligned sunlight, and coherent environment lighting. Use for architectural skies, outdoor 3D backgrounds, golden hour, and day-to-night sky transitions.
- **3d-sky-rays** (+agents/) — Add sun shafts and crepuscular rays to a Three.js or equivalent 3D scene, using scene occlusion, a projected sun position, controlled foreground spill, and scalable post-processing. Use for rays of light from the sky, sunlight through trees or roofs, and golden-hour architectural scenes.
- **3d-virtual-tour** (+agents/) — Build guided and interactive virtual tours through a 3D environment with authored camera paths, room and floor-plan navigation, orbit inspection, smooth mode handoffs, and progressive loading. Use for architectural walkthroughs, real-estate tours, museums, showrooms, and explorable spaces built with Three.js or a similar renderer.