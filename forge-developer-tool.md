# Brand: Forge
> A CI/CD platform for developer teams who value signal over noise — fast, precise, zero ceremony.

**Source:** Brief — all tokens inferred.

---

## Visual Identity

**Aesthetic:** Dark precision
**Mode:** Dark (light mode not supported — dark is the product, not a preference)
**References:** Vercel's deployment UI (dark, confident, instant feedback), Linear's information density, Railway's minimal confidence
**Never look like:** Enterprise IT dashboard (grey, bloated, form-heavy). Startup landing page (gradients, celebration animations). GitHub Actions logs (unstyled, utilitarian to a fault).

---

## Colors

Primary: #E8F0FE — Pale Blue — primary actions, active states, links, focus rings
Secondary: #4A72D4 — Electric Blue — hover states, interactive depth, secondary actions
Accent: #F5A623 — Amber — pipeline warnings, build alerts, attention states — used only for status, never decoration
Background: #0D0D0F — Near Void — primary page base; dark but warm-neutral, not cold blue-black
Surface: #161618 — Carbon — cards, panels, sidebars
Surface Raised: #1E1E21 — Lifted Carbon — dropdowns, tooltips, popovers, hover targets
Border: #2A2A30 — Dim Line — all dividers, table lines, panel edges
Text Primary: #F0F0F2 — Near White — headings and body; not pure white — reduces harshness
Text Secondary: #7A7A85 — Mid Grey — metadata, timestamps, secondary labels
Text Disabled: #4A4A55 — Dark Grey — disabled states
Success: #3ECF8E — Terminal Green — pipeline passed, deployment successful
Warning: #F5A623 — Amber — same as accent; build warnings, degraded state
Error: #E84040 — Hot Red — pipeline failed, deployment error, critical alerts
Info: #60A5FA — Sky — neutral informational states

Status color system (pipeline stages):
Queued: #4A4A55
Running: #4A72D4
Passed: #3ECF8E
Failed: #E84040
Cancelled: #7A7A85
Skipped: #4A4A55

**Color psychology:**
Near-void dark base creates focus — everything else pops against it, making information hierarchy effortless. Electric blue as interactive color is familiar to developers (browser focus rings, IDE highlights) without being generic. Amber reserved strictly for warning/attention means it carries real signal value rather than decoration.

**Color rules:**
- Amber appears ONLY on warning/attention states. Never as a general accent or highlight color.
- Background and Surface are both dark but visibly distinct — never flatten them to the same value.
- Status colors are used consistently across the entire product — Running is always #4A72D4, Passed is always #3ECF8E.

**Dark mode overrides:** N/A — dark mode IS the product. This design is dark-only.

---

## Typography

Heading: Inter — https://fonts.google.com/specimen/Inter
Why: Developer tools demand zero personality friction — Inter is the native language of the tools this audience already uses daily, making the UI feel immediately familiar and legible.

Body: Inter — https://fonts.google.com/specimen/Inter
Why: Single-family reduces cognitive load — developers reading logs, configs, and error messages don't need typographic variety; consistency is the feature.

Mono: JetBrains Mono — https://fonts.google.com/specimen/JetBrains+Mono
For: All code, commands, pipeline names, build IDs, branch names, duration values, file paths, log output, any technical string.

**Type scale:**
- Display: 40px / 700 / 1.1 — rare; page titles only
- H1: 28px / 600 / 1.15
- H2: 20px / 600 / 1.2
- H3: 15px / 600 / 1.3
- H4: 13px / 600 / 1.35
- Body LG: 16px / 400 / 1.6
- Body: 14px / 400 / 1.55 — default; compact for data density
- Body SM: 12px / 400 / 1.45 — log lines, metadata
- Label: 11px / 500 / 1.4 — uppercase, letter-spacing 0.08em
- Code: 13px / 400 — mono font

**Typography rules:**
- Pipeline names, build IDs, branch names, durations ALWAYS in mono — never in Inter
- Type scale small by design — developer tools pack information; legibility not size is the priority
- Display text reserved for empty states and onboarding; normal product views use H1–H3

---

## Spacing & Layout

Base unit: 4px — tighter base for data density
Scale: 4, 8, 12, 16, 24, 32, 48, 64
Max content width: 1440px
Grid: 12-column, 16px gutter, persistent left nav sidebar
Density: Compact — developers work in this all day and need maximum information; empty space is wasted screen real estate

---

## Border Radius

sm: 4px — badges, input fields, table cells
md: 6px — cards, buttons, dropdowns
lg: 10px — modals, side panels
full: 9999px — status pills only

**Radius personality:** Minimal. Developer tools are precise and functional. Every pixel of rounding is a pixel of authority spent.

---

## Shadows & Elevation

[Dark mode elevation uses lightness, not shadows. Shadow values still needed for popover/modal overlays against the dark base.]

sm: 0 1px 2px rgba(0,0,0,0.4) — minimal lift
md: 0 4px 8px rgba(0,0,0,0.5) — dropdowns, command palette
lg: 0 8px 24px rgba(0,0,0,0.6) — modals
xl: 0 16px 48px rgba(0,0,0,0.7) — max-elevation overlays

**Shadow personality:** Deep, heavy shadows appropriate for dark backgrounds — the contrast makes panels feel properly elevated against the dark base.
**Shadow rules:**
- Cards use Surface Raised for elevation, not shadows — light-through-surface is the primary elevation language
- Shadows reserved for floating layers (dropdowns, modals) that appear above the page

---

## Motion & Animation

**Personality:** Instant and purposeful — motion is for orientation only; developers expect immediate feedback and any perceptible delay on a UI action reads as a bug.

**Durations:**
- Instant: 80ms — button press, toggle
- Fast: 100ms — hover states, border changes
- Base: 180ms — panel transitions, sidebar
- Slow: 300ms — page-level transitions (rare)

**Easing:**
- Enter: ease-out
- Exit: ease-out (consistent — no special exit easing)
- Move: ease-in-out

**Named transitions:**
- transition-hover: 80ms ease-out
- transition-enter: 180ms ease-out
- transition-exit: 120ms ease-out
- transition-layout: 180ms ease-in-out

**Never:** Page transition animations. Skeleton loaders where data loads fast. Celebration effects. Anything that adds perceived latency. Bounce. Parallax. Auto-play video. Spinning loaders (use linear progress bars).

**prefers-reduced-motion:** All transitions collapse to instant. No exceptions.

---

## Components

**Buttons:**
- Primary: #4A72D4 bg, #F0F0F2 text, 6px radius, no shadow, hover: lighten 8%, 32px height (compact)
- Secondary: transparent, #2A2A30 border 1px, #F0F0F2 text, hover: Surface Raised bg
- Ghost: Text Secondary, no border, Text Primary on hover
- Destructive: #E84040 bg, white text
- Disabled: 30% opacity, cursor: not-allowed
- Rules: No gradients. No shadows. Flat. 32px default height for compact density.

**Cards:**
- Default: Surface (#161618) bg, Border 1px, 6px radius, 16px padding, no shadow
- Hover: border shifts to #3A3A42, no shadow, no lift
- Pipeline cards: left border 3px in status color (Queued/Running/Passed/Failed/Cancelled)

**Inputs:**
- Surface Raised bg, Border 1px, 4px radius, Text Primary
- Focus: Secondary (#4A72D4) border 1.5px, no glow
- Mono font for code/command inputs

**Navigation:**
- Left sidebar, fixed, Surface bg, Border-right 1px
- Active: Secondary left border 3px + Text Primary
- Inactive: Text Secondary
- No top nav — full left sidebar pattern

**Badges & Labels:**
- Status: use defined status color system — left border 3px OR background tint + matching text
- Always uppercase, Label font size, tracked

**Icons:**
- Set: Lucide Icons
- Style: 1.5px stroke, outline only
- Size: 14px inline, 16px standalone, 20px feature
- Color: Text Secondary default, Text Primary on hover/active

---

## Code

### CSS Variables

```css
:root {
  --color-primary: #E8F0FE;
  --color-secondary: #4A72D4;
  --color-accent: #F5A623;
  --color-background: #0D0D0F;
  --color-surface: #161618;
  --color-surface-raised: #1E1E21;
  --color-border: #2A2A30;
  --color-text-primary: #F0F0F2;
  --color-text-secondary: #7A7A85;
  --color-text-disabled: #4A4A55;
  --color-success: #3ECF8E;
  --color-warning: #F5A623;
  --color-error: #E84040;
  --color-info: #60A5FA;

  --color-status-queued: #4A4A55;
  --color-status-running: #4A72D4;
  --color-status-passed: #3ECF8E;
  --color-status-failed: #E84040;
  --color-status-cancelled: #7A7A85;

  --font-heading: 'Inter', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;

  --text-display: 40px; --text-h1: 28px; --text-h2: 20px;
  --text-h3: 15px; --text-h4: 13px; --text-body-lg: 16px;
  --text-body: 14px; --text-body-sm: 12px; --text-label: 11px; --text-code: 13px;

  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-6: 24px; --space-8: 32px; --space-12: 48px; --space-16: 64px;

  --radius-sm: 4px; --radius-md: 6px; --radius-lg: 10px; --radius-full: 9999px;

  --shadow-sm: 0 1px 2px rgba(0,0,0,.4);
  --shadow-md: 0 4px 8px rgba(0,0,0,.5);
  --shadow-lg: 0 8px 24px rgba(0,0,0,.6);
  --shadow-xl: 0 16px 48px rgba(0,0,0,.7);

  --duration-instant: 80ms; --duration-fast: 100ms; --duration-base: 180ms; --duration-slow: 300ms;
  --ease-enter: ease-out; --ease-exit: ease-out; --ease-move: ease-in-out;
  --transition-hover: 80ms ease-out;
  --transition-enter: 180ms ease-out;
  --transition-layout: 180ms ease-in-out;
}
```

### Tailwind Extension

```js
colors: {
  primary: '#E8F0FE', secondary: '#4A72D4', accent: '#F5A623',
  background: '#0D0D0F', surface: '#161618', 'surface-raised': '#1E1E21',
  border: '#2A2A30', 'text-primary': '#F0F0F2', 'text-secondary': '#7A7A85',
  'text-disabled': '#4A4A55', success: '#3ECF8E', warning: '#F5A623',
  error: '#E84040', info: '#60A5FA',
  'status-queued': '#4A4A55', 'status-running': '#4A72D4', 'status-passed': '#3ECF8E',
  'status-failed': '#E84040', 'status-cancelled': '#7A7A85',
},
fontFamily: {
  heading: ['Inter', 'system-ui', 'sans-serif'],
  body: ['Inter', 'system-ui', 'sans-serif'],
  mono: ['"JetBrains Mono"', '"Courier New"', 'monospace'],
},
borderRadius: { sm: '4px', md: '6px', lg: '10px' },
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. **Colors:** Dark mode only. Background #0D0D0F for pages, Surface #161618 for cards, Surface Raised #1E1E21 for nested elements. Never introduce light backgrounds.
2. **Typography:** Inter for all headings and body. JetBrains Mono for ALL code, commands, IDs, paths, durations, and technical strings — no exceptions.
3. **Status system:** Pipeline/build status uses the defined 5-color system. Never improvise status colors. Queued/Running/Passed/Failed/Cancelled are fixed.
4. **Spacing:** 4px base unit, compact scale. 16px card padding, 32px button height. Do not over-space.
5. **Motion:** 80–180ms. Instant feel. No page transition animations. No skeletons where data loads fast. Nothing that adds perceived latency.
6. **Amber is status only:** Never use --color-accent decoratively. Warning/attention states only.
7. **Scope:** This file controls visuals only. Do NOT change copy, content, features, or UX structure.
8. **Archetype check:** Would a developer using this at 2am during an incident find it clear and fast? If there's any visual noise or anything slow, remove it.
