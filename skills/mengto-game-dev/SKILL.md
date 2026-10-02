---
name: mengto-game-dev
description: "Use when building, tuning, testing or shipping a Three.js / web game: mobile controls, camera, combat, enemies, AI, VFX, audio, levels, inventory, performance, QA, deploy. Index of 20 MengTo game-development skills fetched on demand."
---

# MengTo game-development skills — index + fetch on demand

מאגר: https://github.com/MengTo/Skills (תיקייה `agent-skills/game-development/`). הסקילים עצמם לא מוטמעים כאן — מושכים אותם מהמאגר בזמן העבודה, כך שהם תמיד מעודכנים.

## איך להשתמש

1. מצא ברשימה למטה את הסקיל (או 2–3 סקילים) שהכי מתאים למשימה. אם המשתמש ביקש אפקט/סגנון ספציפי, העדף את הסקיל הצר ביותר שמכסה אותו.
2. משוך את ה-SKILL.md המלא:
   `WebFetch("https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/game-development/<slug>/SKILL.md", "Return the full file verbatim")`
   (אם WebFetch מקצר — בקש חלקים: "Return lines 1-200 verbatim", וכו'.)
3. אם ה-SKILL.md מפנה לקבצים יחסיים (`references/…`, `agents/…`, `assets/…`, `scripts/…`) — משוך אותם מאותה תיקייה:
   `https://raw.githubusercontent.com/MengTo/Skills/main/agent-skills/game-development/<slug>/<relative-path>`
   קבצים בינאריים (תמונות/mp4) אי אפשר למשוך — דלג עליהם.
4. עקוב אחרי ההוראות בסקיל שנמשך במלואן. הן גוברות על ברירות מחדל שלך.
5. אם המשיכה נכשלת — אמור למשתמש, ואל תמציא את תוכן הסקיל.

## הרשימה (20)

- **author-game-levels** (+agents/) — Author or revise readable, flat-world Three.js game levels. Use for movement and camera routes, collision and navigation, encounter zones, landmarks, objectives, pickups, motivated lighting, visibility, deterministic level data, or desktop and mobile playthrough verification.
- **build-game-audio-feedback** (+agents/) — Design or implement responsive audio feedback for a Three.js or web game. Use for action sounds, combat layers, music states, spatial audio, mix priorities, mute controls, accessibility, mobile audio unlock, and audio performance.
- **build-game-camera-controls** (+agents/) — Implement or tune Three.js game cameras. Use for isometric framing, follow behavior, orbit/zoom limits, occlusion, lock-on, camera shake, touch camera controls, and camera regression tests.
- **build-game-changelog** (+agents, references/) — Design, implement, backfill, audit, and release in-game changelogs with contiguous versioning, deployment provenance, menu-state navigation, accessible toggle, close, and Escape behavior, and responsive release-ledger UI. Use when adding or revising a changelog or version screen in a game, reconstructing release history from deployments and Git, defining version-bump rules, keeping displayed versions synchronized with live builds, or testing changelog mechanics across desktop and mobile.
- **build-game-inventory** (+agents/) — Build or repair game inventory, loot, equipment, tooltips, drag-and-drop, persistence, and progression systems. Use for item schemas, pickup flows, stack rules, equipment slots, atomic swaps, save migration, and no-loss regression testing.
- **build-game-map-editor** (+agents, references/) — Build, extend, or audit production-linked browser map editors for Three.js and isometric games. Use for a private director view, a versioned editor document from authored placements, outliner/layer/selection/drag/snap/inspector/camera controls, enemy aggro/leash/patrol overlays, local draft import/export/undo/reset, securing an editor route, or validating and releasing a map editor without mutating live gameplay data.
- **build-game-monster-system** (+agents, references/) — Build, integrate, audit, or refactor rigged monsters for Three.js and web action games. Use for monster asset contracts, procedural or imported creature rigs, semantic joints and sockets, hurtboxes and attack volumes, combat animation states, enemy-runtime adapters, LODs, deterministic review fixtures, and validating that every monster follows one shared system.
- **build-hybrid-game-assets** (+agents/) — Plan, create, integrate, or audit a hybrid asset pipeline for a Three.js or web game. Use when choosing among imported meshes, procedural 3D geometry, AI-generated reference art, 2D UI media, sprites, VFX, and performance-ready runtime asset delivery.
- **build-isometric-arpg** (+agents/) — Build or extend a playable isometric action RPG in Three.js, React, or similar web technology. Use for game-loop architecture, camera and movement, zones, combat integration, content data, progression, saves, or production-ready vertical slices.
- **build-mobile-threejs-games** (+agents/) — Build, tune, or test a Three.js game for mobile web. Use for touch movement, action controls, target selection, touch inventory, safe areas, portrait/landscape layouts, responsive HUD, battery/performance budgets, and real mobile browser QA.
- **build-rigged-game-assets** (+agents, assets, references, scripts/) — Create, integrate, or audit production-ready rigged 3D characters and monsters with a main model, skeleton, animation library, sockets, collision contracts, separate character equipment, optimized runtime files, catalog media, and an interactive moveset inspector. Use when generating or importing FBX/GLB game actors; separating swords, shields, helmets, armor, or stowed gear; adding idle, walk, run, attack, hit, dodge, block, cast, or death clips; wiring an asset into gameplay.
- **build-threejs-enemy-systems** (+agents/) — Build or refactor reusable, data-driven enemy archetype and moveset systems for Three.js action games. Use for enemy content schemas, model and rig conventions, combat move timing and contact contracts, runtime state boundaries, placeholder fallbacks, deterministic fixtures, or production playthrough validation.
- **build-vesperfall-review-assets** (+agents, references, scripts/) — Build truthful asset-library review pairs from transparent PNG references and live Three.js, FBX, or img2threejs models (MengTo's Vesperfall catalog pattern). Use for card-PNG plus inspector-model treatment, isolated model or moveset routes, provenance, grounding, tests, and browser validation for game art review.
- **create-game-vfx** (+agents/) — Create readable, performance-safe Three.js game visual effects. Use for attacks, impacts, damage feedback, status effects, spell trails, particles, shaders, telegraphs, quality tiers, and reduced-motion alternatives.
- **design-action-combat** (+agents/) — Design, implement, tune, or test readable tactical action combat for web games. Use for attack timing, guard and dodge windows, hit contact, posture, lock-on, weapons, boss phases, combat feedback, and deterministic combat tests.
- **design-game-encounters** (+agents/) — Design, implement, tune, or test Three.js action-game encounters. Use for arena layout, enemy composition, spawn pacing, objectives, boss phases, reward cadence, encounter fixtures, and difficulty validation.
- **optimize-threejs-games** (+agents/) — Profile, diagnose, and improve Three.js or WebGL game performance without regressing gameplay. Use for frame-time drops, CPU/GPU pressure, draw calls, texture and geometry budgets, animation loops, adaptive quality, mobile performance, and browser performance verification.
- **ship-web-games** (+agents/) — Package, deploy, and verify a playable Three.js or web game. Use for release builds, asset delivery, private/public deployment, production smoke tests, browser proof, release notes, rollback readiness, and cleanup of temporary QA resources.
- **test-playable-web-games** (+agents/) — Test a playable browser game end to end with deterministic fixtures and real browser evidence. Use for gameplay QA, regression testing, controls, accessibility, responsive/mobile testing, save flows, console checks, performance smoke tests, and release verification.
- **tune-enemy-ai** (+agents/) — Build, debug, balance, or test combat enemy AI for playable action games. Use for aggro, target selection, navigation, spacing, attack choices, telegraphs, retreats, boss behavior, behavior-state machines, and deterministic AI regression tests.