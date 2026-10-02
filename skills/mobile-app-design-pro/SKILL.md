---
name: mobile-app-design-pro
description: "Professional mobile app design rules (single-file PWA/HTML, native Android, iOS): design tokens, Hebrew RTL, typography, touch, navigation, states, and professional animation/motion. Use whenever building or polishing phone UI."
---

# Professional Mobile App Design

Goal: every screen produced here must look like a store-quality app, not a web page. Rules are distilled from Apple HIG (iOS 26 / Liquid Glass), Material 3 Expressive (motion physics system), web.dev PWA guidance, Chrome View Transitions docs, and Hebrew RTL best practices. Defaults: Hebrew, RTL, Android-first, single HTML file — unless told otherwise.

## 0. Workflow (mandatory, before writing code)
1. Define **one token system** (color, type, spacing, radius, shadow, motion) as CSS variables / Compose theme. Never hard-code a value inside a screen.
2. Sketch the **screen map + navigation** (max 5 destinations in the bottom bar). Every screen has four states: normal, empty, loading, error.
3. Build one complete screen, test at 360×800 (common Android) and 390×844 (iPhone) — only then replicate the language to the rest.
4. Finish with the checklist in section 12.

## 1. Spacing & sizing
- **8dp/pt grid** with 4-unit subdivisions. Allowed spacing: 4, 8, 12, 16, 24, 32, 48.
- Screen side margins: **16** (Android) / 16–20 (iOS). Wide screens (>600): 24.
- **Minimum touch target: 48×48dp** (Material) / 44×44pt (iOS). Primary button height 48–56. Gap between targets ≥ 8.
- Thumb zone: primary actions in the bottom half / center. Destructive or rare actions at the top or behind a menu.
- Radius: small 8, medium 12, large 16–20, cards 16, bottom sheets 28 on top, pill buttons `9999px`.
- Max 3 depth levels per screen (background → card → floating action).

## 2. Typography
- **One font family max** (+ mono for code/numbers only if needed). Hierarchy through weight and size, never through font switching.
- Hebrew: `'Heebo', 'Assistant', 'Rubik', 'Noto Sans Hebrew', system-ui, sans-serif`. In a PWA preload with `<link rel="preload" as="font">` or use `font-display: swap`.
- English/system: `-apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif`.
- Recommended scale (px/sp): Display 32–36 bold · Title 22 semibold · Headline 17–18 semibold · Body **16** regular (Hebrew never below 16) · Secondary 14 · Caption 12 · Label minimum 11.
- Line-height: body 1.5–1.7 for Hebrew, headings 1.2. **Never apply letter-spacing to Hebrew.**
- Secondary text = same color at 60% opacity, not a random gray.
- Screen title: large (32–34) at top collapsing to a small centered title on scroll (iOS pattern), or a 56–64dp top bar (Material).
- Use relative `font-size` (rem) and never block user zoom (`user-scalable=no` is forbidden except in games).

## 3. Color
- Define **roles**, not colors: `--bg`, `--surface`, `--surface-2`, `--on-surface`, `--on-surface-2` (60%), `--primary`, `--on-primary`, `--primary-container`, `--outline`, `--error`, `--success`, `--warning`.
- Contrast: body text **≥ 4.5:1**, large text/icons ≥ 3:1. Actually verify it.
- One primary color + one accent, maximum. Everything else neutral (a gray scale tinted slightly toward the primary — never pure gray).
- **Dark mode is mandatory** via `prefers-color-scheme` + `<meta name="color-scheme" content="light dark">`. Dark: background `#121212`–`#0F0F12` (not pure black), surfaces get lighter with elevation, primary slightly brighter and less saturated, text white at 87%.
- `theme-color` meta updates per scheme (`media="(prefers-color-scheme: dark)"`).
- Material 3 Expressive: large tonal containers (primary-container) for emphasized buttons and cards; only one full-color primary action per screen.

## 4. Screen structure & navigation
- **Bottom navigation bar**: 3–5 destinations, icon + 11–12sp label, height 64–80 + `safe-area-inset-bottom`. Active item: primary color + pill background (M3) or color only (iOS). iOS 26: floating Liquid Glass bar inset ~21pt from the edges.
- **Top bar**: title, back (arrow mirrors in RTL), up to 2 actions. On scroll: light shadow/blur, no height jump.
- **FAB** for a single dominant action (create/record). 56dp, bottom corner on the inline-end side — position with `inset-inline-end` and let the engine flip it for RTL.
- **Bottom sheet** instead of dialog for most choices. Drag handle 32×4, top radius 28, dismiss by drag and by tapping the scrim.
- **Dialog** only for destructive confirmation / binary decisions. Destructive button in red; the confirm action is always last in reading order.
- Back: support both edge swipe (iOS) and the system back (Android) — in a PWA listen to `popstate` and manage history yourself.
- Full-screen modal on iOS slides up from the bottom, closes with an X at the top-leading corner or a swipe down.

## 5. Components — fixed patterns
- **Buttons**: Filled (primary, one per screen), Tonal (secondary, primary-container), Outlined, Text. Height 48, horizontal padding 24, pill or radius 12. Pressed: `scale(0.97)` + 8–12% darken in 100ms. Disabled: 38% opacity, not another gray.
- **Inputs**: height 56, floating or top label, `dir="auto"` on every input, correct `inputmode` (`tel`, `numeric`, `email`), `autocomplete`, error message below in error color + icon, never color alone.
- **Lists**: row 56–72dp, icon/image at inline-start, chevron at inline-end (mirrors in RTL), subtle divider (`--outline` at 12%) or no divider with spacing.
- **Cards**: radius 16, padding 16, no shadow in dark mode (use surface tint), subtle shadow in light: `0 1px 3px rgba(0,0,0,.08), 0 4px 12px rgba(0,0,0,.06)`.
- **Chips / button groups** (M3 Expressive): pill, height 32–40, selected = primary-container.
- **Toast/Snackbar**: bottom, above the nav bar, 4 seconds, one action max.
- **Loading**: skeleton for screens, small spinner inside the button (button keeps its width), linear progress for processes > 5 seconds. Never a blank white screen.
- **Empty state**: large illustration/icon + one sentence + action button. This is a disguised onboarding screen.
- **Error**: what happened + what to do + a "Try again" button. Never show a technical error code to the user.

## 6. Professional animation & motion

### 6.1 Principles (Apple HIG + Material 3 Expressive)
- Motion has a job: show where something came from / went to, confirm an action, or reveal hierarchy. If you cannot name the job, delete the animation.
- Feedback motion is **brief and precise**. Frequent interactions (tapping a list row, toggling) get the subtlest motion; hero moments (first launch, completing a task, opening a detail) get the most.
- Motion follows the gesture: a sheet dragged up is dismissed down; a card that expanded from a thumbnail collapses back into it. Never dismiss in a different direction than the reveal.
- Everything is **interruptible and cancellable**: the user never waits for an animation to finish before the next tap works. Springs handle this natively; if using CSS transitions, make new transitions start from the current computed value (don't reset).
- Motion is optional: pair it with haptics/color so meaning survives `prefers-reduced-motion`.
- One motion scheme per product. Material offers two: **Expressive** (overshoot + bounce, for consumer apps and hero moments — the default here) and **Standard** (eases in, no bounce, for utilitarian tools). Do not mix them within a screen except deliberately for a hero.

### 6.2 Two kinds of motion, two kinds of curves
- **Spatial** = position, size, rotation, corner radius. Spatial motion may **overshoot** (spring bounce).
- **Effects** = opacity, color, blur, shadow. Effects **never overshoot** (a color bouncing past its target looks broken).
- Three speeds: **fast** for small components (switches, buttons, chips), **default** for elements covering part of the screen (bottom sheets, menus, nav rail), **slow** for full-screen moves.

### 6.3 Material 3 motion tokens — exact web values
Define these once as CSS variables and use them everywhere. Values are Material's official spring-to-curve conversions.
```css
:root {
  /* Expressive scheme (default) */
  --m-fast-spatial:    350ms cubic-bezier(0.42, 1.67, 0.21, 0.90);
  --m-default-spatial: 500ms cubic-bezier(0.38, 1.21, 0.22, 1.00);
  --m-slow-spatial:    650ms cubic-bezier(0.39, 1.29, 0.35, 0.98);
  --m-fast-effects:    150ms cubic-bezier(0.31, 0.94, 0.34, 1.00);
  --m-default-effects: 200ms cubic-bezier(0.34, 0.80, 0.34, 1.00);
  --m-slow-effects:    300ms cubic-bezier(0.34, 0.88, 0.34, 1.00);
  /* Standard scheme (utilitarian, no bounce) */
  --s-fast-spatial:    350ms cubic-bezier(0.27, 1.06, 0.18, 1.00);
  --s-default-spatial: 500ms cubic-bezier(0.27, 1.06, 0.18, 1.00);
  --s-slow-spatial:    750ms cubic-bezier(0.27, 1.06, 0.18, 1.00);
  /* Legacy M3 easing when a plain curve is needed */
  --ease-emphasized:   cubic-bezier(0.2, 0, 0, 1);
  --ease-emphasized-decel: cubic-bezier(0.05, 0.7, 0.1, 1);   /* entering */
  --ease-emphasized-accel: cubic-bezier(0.3, 0, 0.8, 0.15);   /* exiting */
}
```
- Curves with a Y value > 1 (e.g. `1.67`, `1.21`) are the overshoot. Only use them on `transform`, never on `opacity`/`color`.
- Exits are faster than entrances (accelerate out, decelerate in). Exit ≈ 60–70% of the entrance duration.
- Native Compose: use `MaterialTheme.motionScheme` tokens (`fastSpatialSpec()`, `defaultSpatialSpec()`, `fastEffectsSpec()` …) via `MaterialExpressiveTheme`; never hand-write `tween()` durations for standard components.
- iOS/SwiftUI: `.spring(duration: 0.5, bounce: 0.3)` for spatial, `.smooth` / `.easeOut(duration: 0.2)` for effects. `.bouncy` only for hero moments.

### 6.4 Duration ladder (when not using the tokens above)
- Micro feedback (press, toggle, checkbox): 100–150ms.
- Component in/out (chip, menu, tooltip, snackbar): 200–250ms.
- Container (bottom sheet, dialog, expanding card): 300–400ms.
- Full-screen transition: 350–500ms.
- Anything > 500ms must be either a hero moment or a progress indicator. Nothing UI-related exceeds 700ms.

### 6.5 Performance rules (non-negotiable on phones)
- Animate **only** `transform` and `opacity`. These run on the compositor at 60/120fps. `height`, `width`, `top/left`, `margin`, `padding`, `box-shadow`, `border-radius`, `filter: blur()` trigger layout/paint — they jank on mid-range Android.
- Fake the expensive ones: shadow change → crossfade two pre-rendered shadow layers; height change → `scaleY` with `transform-origin` or `grid-template-rows: 0fr → 1fr` (cheap enough); blur → crossfade a pre-blurred layer.
- `will-change: transform` only on the element about to animate, and remove it afterwards. Never on many elements at once (GPU memory).
- Prefer the **Web Animations API** (`el.animate()`) over CSS keyframes for anything driven by JS: it is interruptible (`anim.cancel()`, `anim.reverse()`), composable, and runs off-main-thread when animating transform/opacity.
- Never animate on `scroll` events in JS; use `animation-timeline: scroll()` / `view()` (scroll-driven animations) or `IntersectionObserver` with CSS classes.
- Test on a real mid-range Android device with 4x CPU throttling in DevTools. If it drops frames there, simplify.

### 6.6 Screen transitions in a single-file PWA
- Use the **View Transition API** for route changes; fall back gracefully:
```js
function go(render) {
  if (!document.startViewTransition) return render();
  document.startViewTransition(render);
}
```
```css
@view-transition { navigation: auto; }            /* MPA only */
::view-transition-old(root) { animation: 200ms var(--ease-emphasized-accel) both fade-out, 300ms var(--ease-emphasized) both slide-out; }
::view-transition-new(root) { animation: 250ms var(--ease-emphasized-decel) both fade-in,  300ms var(--ease-emphasized) both slide-in; }
.hero-img { view-transition-name: hero; }          /* shared element: thumbnail → detail */
```
- Forward navigation: new screen slides in from inline-end (mirrors in RTL) or fades + scales from 0.96; old screen dims slightly and moves 20–30% of the distance (parallax). Back navigation: the exact reverse.
- Shared-element transitions (image/card → detail) are the single biggest "feels native" upgrade. Use `view-transition-name` on the element in both states; give each name to exactly one element at a time.
- Bottom sheet: `translateY(100%) → 0` with default-spatial; scrim fades with default-effects. Follow the finger during drag (`touchmove` → `transform` directly, no transition), then spring to the nearest snap point on release; dismiss if velocity > 0.5px/ms or dragged > 40% down.
- Keep the bottom nav bar and header **static** during screen transitions (they are shared chrome). Only the content area moves.

### 6.7 Micro-interactions catalog (copy these)
- **Press**: `transform: scale(0.97)` in 100ms on `:active`/`pointerdown`, release back with fast-spatial (slight overshoot). Add `navigator.vibrate?.(8)` on Android for primary actions only.
- **Toggle/switch**: thumb slides with fast-spatial, track color with fast-effects, thumb grows 10% while pressed (M3 Expressive).
- **Checkbox/success**: draw the checkmark with `stroke-dashoffset` over 250ms, then a 1.1 → 1 scale pop with fast-spatial.
- **Like/favorite**: scale 1 → 1.3 → 1 with fast-spatial + color fill with fast-effects; optional particle burst is a hero moment — use once, not on every tap.
- **List item enter**: stagger children by 30–50ms, max 8 staggered items (rest appear instantly); each item `translateY(12px) + opacity 0 → 1` with default-effects/spatial.
- **Skeleton shimmer**: a 1.5s linear gradient sweep, `background-position` animation is OK here since the element is static; stop it when content arrives.
- **Pull-to-refresh**: indicator follows finger with resistance (`dy * 0.5`), spins at threshold, springs back with default-spatial.
- **FAB → sheet / FAB menu**: container transform — FAB morphs (scale + border-radius via `clip-path` or two-layer crossfade) into the sheet over 400ms; icons in the menu stagger in.
- **Number change** (counter, price): crossfade + `translateY` digit roll, 200ms effects. Never let text jump width — use `font-variant-numeric: tabular-nums`.
- **Empty → content**: crossfade 200ms; do not slide the whole screen.
- **Error shake**: `translateX` ±6px, 3 cycles, 300ms total, only on the field that failed, plus haptic error pattern `vibrate([30, 40, 30])`.

### 6.8 Gesture-driven motion
- Gestures map 1:1 to the finger while touching (no easing during drag); easing/spring applies only on release.
- Use release **velocity** to pick the target and the spring's initial velocity, so a fast flick travels further than a slow drag.
- Rubber-band at edges: displacement = `d * 0.55` past the limit, spring back on release.
- `touch-action: pan-y` (or `none`) on gesture surfaces so the browser doesn't fight you; `pointer` events, not `touch` events, for unified mouse/pen/finger.

### 6.9 Reduced motion & accessibility
- `@media (prefers-reduced-motion: reduce)`: replace movement with 150ms crossfades, disable parallax/stagger/auto-playing loops, keep functional progress indicators.
- Nothing flashes more than 3 times per second. No sustained oscillation.
- Motion never carries information alone: pair with color, icon, text or haptic.

### 6.10 Motion review checklist
- [ ] Every animation has a nameable purpose.
- [ ] Only `transform`/`opacity` animate (except shimmer and `grid-template-rows` tricks).
- [ ] Spatial curves may overshoot; effects curves never do.
- [ ] Entrances decelerate, exits accelerate and are shorter.
- [ ] Tapping during an animation works immediately (interruptible).
- [ ] Shared chrome (nav bar, header) stays still during screen transitions.
- [ ] Runs at 60fps on a mid-range Android with 4x CPU throttle.
- [ ] Reduced-motion variant exists and is tested.

## 7. RTL & Hebrew — hard rules
- `<html lang="he" dir="rtl">`. **Forbidden**: `margin-left/right`, `padding-left/right`, `left/right`, `text-align: left/right`. Only logical: `margin-inline-start/end`, `padding-inline-*`, `inset-inline-*`, `text-align: start`, `border-inline-*`.
- Never add `flex-direction: row-reverse` "to fix" RTL — that is a double flip.
- **Mirror (scaleX(-1))**: navigation/back arrows, chevrons, send, undo/redo, list indent, directional progress. **Do not mirror**: logos, ✓, ✕, play/pause, clocks, numbers, media.
- Numbers, phone numbers, code, URLs, runs of English: `<span dir="ltr">` or `<bdi>`, `unicode-bidi: isolate`. Test string: `שלום John 050-1234567 ₪1,234`.
- Format numbers/dates with `Intl.NumberFormat('he-IL')` / `Intl.DateTimeFormat`.
- Sliders, carousels, progress, charts — the X axis flips. Fixed elements (toast, FAB, header) — only `inset-inline`.
- Slide transitions mirror too: "forward" enters from inline-end. Write `translateX` values through a CSS variable set per direction (`--dir: 1` in LTR, `-1` in RTL → `translateX(calc(var(--dir) * 100%))`).
- Niqqud and final letters: make sure the font supports them (Heebo/Assistant/Rubik do).
- Hebrew text tends to run 10–20% longer than English — buttons with `min-width` not fixed width, ellipsis for single-line text.

## 8. PWA / single-file HTML — required boilerplate
```html
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="color-scheme" content="light dark">
<meta name="theme-color" content="#FFFFFF" media="(prefers-color-scheme: light)">
<meta name="theme-color" content="#121212" media="(prefers-color-scheme: dark)">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="google" content="notranslate">
<link rel="apple-touch-icon" sizes="180x180" href="icon-180.png"> <!-- square, no transparency, no rounded corners -->
<link rel="manifest" href="manifest.webmanifest"> <!-- display: standalone, icons 192+512 with purpose maskable, theme_color, background_color, lang: he, dir: rtl -->
```
```css
:root { color-scheme: light dark; }
html, body { height: 100%; margin: 0; }
body {
  min-height: 100dvh;
  padding-top: env(safe-area-inset-top);
  padding-bottom: env(safe-area-inset-bottom);
  overscroll-behavior-y: contain;      /* no pull-to-refresh */
  -webkit-text-size-adjust: 100%;
  -webkit-tap-highlight-color: transparent;
  font: 16px/1.6 var(--font);
  background: var(--bg); color: var(--on-surface);
}
button, .tappable { min-height: 48px; min-width: 48px; touch-action: manipulation; user-select: none; -webkit-user-select: none; -webkit-touch-callout: none; }
.scroll { overflow-y: auto; -webkit-overflow-scrolling: touch; overscroll-behavior: contain; }
.bottom-nav { position: fixed; inset-inline: 0; bottom: 0; padding-bottom: env(safe-area-inset-bottom); }
@media (prefers-reduced-motion: reduce) { *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; } }
@media (display-mode: standalone) { /* hide the "install app" prompt */ }
```
- Never use `100vh` (gets clipped behind browser chrome) — only `100dvh` with a `100vh` fallback.
- Keyboard: for inputs near the bottom use `visualViewport` resize to scroll the field into view; never set screen height in px.
- System icons: inline SVG (Material Symbols / Lucide) at 24px, uniform `stroke-width`, `fill: currentColor`. No emoji as UI icons.
- Images: `loading="lazy"`, fixed `aspect-ratio` to avoid layout jumps.
- Performance: first paint < 1.5s, all animation at 60fps, no more than 2 external libraries. `contain: content` on long lists.

## 9. Native Android (Kotlin / Compose)
- `MaterialTheme` with `dynamicColor` (Android 12+) + a static fallback scheme. Material 3 Expressive: `MaterialExpressiveTheme` when available — this also switches all 21+ components to the spring motion system automatically.
- Edge-to-edge: `enableEdgeToEdge()` + `WindowInsets.safeDrawing` / `navigationBars` on scrolling content and on the bottom bar.
- `NavigationBar` with 3–5 items, `LargeTopAppBar` with `scrollBehavior`, `ModalBottomSheet` for choices.
- 48dp minimum: `Modifier.minimumInteractiveComponentSize()`.
- RTL: automatic `LayoutDirection` from `android:supportsRtl="true"` + `PaddingValues(start=…, end=…)`, never left/right. Directional icons: `Icons.AutoMirrored.*`.
- Animation: `animateFloatAsState` / `animateColorAsState` with `MaterialTheme.motionScheme.*Spec()`, `AnimatedVisibility`, `AnimatedContent` with `SizeTransform`, `SharedTransitionLayout` for shared elements between screens, `Modifier.animateItem()` in lazy lists. Never `LaunchedEffect` + manual `delay` loops for UI motion.
- Splash: `SplashScreen API` (androidx.core.splashscreen) with the icon only — no custom loading screen.
- Haptics: `HapticFeedbackType.LongPress` / `TextHandleMove`, not raw vibrate.

## 10. iOS (when relevant / PWA on iPhone)
- Liquid Glass (iOS 26): translucent, blurred navigation layer floating above content; the content itself is never glassy. On the web: `backdrop-filter: blur(20px) saturate(180%)` + 70% background on the header/tab bar only. Liquid Glass reacts more strongly to direct touch than to indirect input — keep glass motion subtle and tactile.
- SF scale: Large Title 34, Title1 28, Title2 22, Title3 20, Headline 17 semibold, Body 17, Subhead 15, Footnote 13, Caption 12/11.
- Home indicator: 21pt reserved at the bottom — `safe-area-inset-bottom` covers it.
- PWA on iOS: no `beforeinstallprompt` — show "Share → Add to Home Screen" instructions only in Safari and not in standalone mode.
- View Transitions API works in Safari 18+; keep the `startViewTransition` fallback for older versions.

## 11. Accessibility (not optional)
- Contrast 4.5:1, touch targets 48, labels on every icon button (`aria-label` / `contentDescription`), logical focus order, never rely on color alone, support Dynamic Type / system font scaling up to 200% without breaking layout.
- `role`, `aria-live="polite"` for toasts, `aria-expanded` for menus.

## 12. Pre-delivery checklist
- [ ] Tested at 360×800 and 390×844, portrait, with the keyboard open, light and dark.
- [ ] No `100vh`, no `left/right`, no `letter-spacing` on Hebrew, no emoji as icons.
- [ ] Every touch target ≥ 48, every text ≥ 12, body 16.
- [ ] Mixed RTL test string renders correctly; directional arrows flipped; ✓/✕/play not flipped; slide transitions mirrored.
- [ ] Four states for every screen: normal / empty / loading / error.
- [ ] Motion checklist in 6.10 passed.
- [ ] Safe areas top and bottom; bottom bar not hidden by the home indicator.
- [ ] `theme-color`, manifest, icons 180/192/512 maskable, splash.
- [ ] One primary action stands out per screen; destructive actions behind confirmation.
- [ ] Lighthouse PWA + Accessibility ≥ 90.

## 13. Professional opinion (defaults when nothing else was decided)
- Android-first with Material 3 Expressive motion, but large radii and clean typography so it also looks right on iPhone.
- One saturated primary color + warm neutrals. No gradients on buttons. No heavy shadows.
- Fewer screens, more bottom sheets. Less text, more whitespace.
- Spend the animation budget on three things: press feedback, screen/shared-element transitions, and one hero moment. Everything else stays nearly still.
- If something looks "like a website" the cause is almost always: inconsistent side margins, text too small, buttons shorter than 48, a white header with a black line, or instant (0ms) state changes. Fix those first.