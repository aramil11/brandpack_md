# Brand: Forge
> A CI/CD platform for developer teams who care about speed and signal — no noise, no dashboards for dashboards' sake.

---

## Visual Identity

**Aesthetic:** Dark precision
**Mode:** Dark
**References:** Vercel (dark, fast, developer-native), Railway (minimal, confident), Linear (opinionated, beautiful)
**Never look like:** An enterprise IT portal (grey, bloated, form-heavy). A startup landing page (gradients, animations, "10x your velocity").

---

## Colors

Primary: #E8F0FE — near-white blue, primary actions, active states, links
Secondary: #4A72D4 — interactive depth, hover states, secondary actions
Accent: #F5A623 — pipeline warnings, build alerts, used only for status
Background: #0D0D0F — near-black page base
Surface: #161618 — cards, panels, modals
Surface 2: #1E1E21 — nested panels, hover targets, elevated surfaces
Border: #2A2A30 — all dividers, table lines, panel edges
Text Primary: #F0F0F2 — headings, body — never pure white
Text Secondary: #7A7A85 — metadata, timestamps, secondary labels
Success: #3ECF8E — pipeline passed, deployment successful
Warning: #F5A623 — build warnings, degraded state
Error: #E84040 — pipeline failed, deployment error

Status colors (for pipeline stages):
- Queued: #4A4A55
- Running: #4A72D4
- Passed: #3ECF8E
- Failed: #E84040
- Cancelled: #7A7A85

Rules:
- Background and Surface are both dark but distinct — never flatten them to the same value
- Accent orange is strictly for warning states. Never use as a decorative color.
- Primary near-white is the only light color used on interactive elements — do not introduce other light colors

---

## Typography

Heading: Inter — https://fonts.google.com/specimen/Inter
Why: Developer tools demand maximum legibility and zero personality friction; Inter is the native language of the tools this audience already uses daily.

Body: Inter — https://fonts.google.com/specimen/Inter
Why: Single-family keeps cognitive load minimal; developers reading logs and configs don't need typographic variety.

Mono: JetBrains Mono — https://fonts.google.com/specimen/JetBrains+Mono
For: All code, commands, pipeline names, build IDs, log output, file paths, duration values.

Scale:
- Display: 44px / 700 — rarely used
- H1: 28px / 600
- H2: 20px / 600
- H3: 15px / 600
- Body: 14px / 400 / line-height 1.55
- Body SM: 12px / 400
- Label: 11px / 500 — uppercase, letter-spacing 0.08em
- Data: 13px / 400 — mono font

Rules:
- Pipeline names, build IDs, branch names always in mono
- Type scale intentionally small — developer tools pack information; legibility not size is the priority
- No display text in normal product views — reserve for empty states and onboarding only

---

## Spacing & Layout

Base unit: 4px
Scale: 4, 8, 12, 16, 24, 32, 48, 64
Max width: 1440px
Grid: 12-column, 16px gutter, persistent left nav
Density: Compact — developers work in this all day and need maximum information density; empty space is wasted screen real estate

---

## Border Radius

sm: 4px — badges, input fields, table cells
md: 6px — cards, buttons, dropdowns
lg: 10px — modals, side panels
full: 9999px — status pills only

Personality: Minimal radius. Developer tools are precise and functional. Rounded corners are a concession to usability, not a personality statement.

---

## Components

Buttons:
- Primary: #4A72D4 background, #F0F0F2 text, 6px radius, no shadow, hover: lighten 8%
- Secondary: transparent, #2A2A30 border 1px, #F0F0F2 text, hover: Surface 2 background
- Ghost: Text Secondary color, no border, Text Primary on hover
- Destructive: #E84040 background, white text
- Rules: No gradients. No shadows. Dense and flat. 32px height default (compact).

Cards:
- Surface background (#161618), Border 1px, 6px radius, 16px padding
- Hover: Border shifts to #3A3A42, no lift or shadow
- Pipeline cards: left border 3px in status color

Inputs:
- Surface 2 background, Border 1px, 4px radius, Text Primary
- Focus: Secondary border (#4A72D4) 1.5px, no glow
- Monospace font for code/command inputs

Navigation:
- Left sidebar, Background color, Border-right 1px
- Active: Secondary left border 3px + Text Primary
- Inactive: Text Secondary

Icons:
- Lucide Icons, 1.5px stroke
- 14px inline, 16px standalone
- Text Secondary default, Text Primary on hover/active

---

## Motion

Personality: Instant and purposeful — developers expect immediate feedback; any perceptible delay on a UI action is a bug.
Default: 100ms ease-out for micro / 180ms ease-out for panel transitions
Hover: Border color shift 80ms. Text color shift 80ms. Nothing else.
Never: Page transition animations. Skeleton loaders on fast data. Celebration effects. Anything that adds perceived latency.

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
  --color-surface-2: #1E1E21;
  --color-border: #2A2A30;
  --color-text-primary: #F0F0F2;
  --color-text-secondary: #7A7A85;
  --color-success: #3ECF8E;
  --color-warning: #F5A623;
  --color-error: #E84040;

  --color-status-queued: #4A4A55;
  --color-status-running: #4A72D4;
  --color-status-passed: #3ECF8E;
  --color-status-failed: #E84040;
  --color-status-cancelled: #7A7A85;

  --font-heading: 'Inter', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;

  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-6: 24px; --space-8: 32px; --space-12: 48px; --space-16: 64px;

  --radius-sm: 4px; --radius-md: 6px; --radius-lg: 10px; --radius-full: 9999px;

  --transition-fast: 100ms ease-out;
  --transition-base: 180ms ease-out;
}
```

### Tailwind Extension

```js
colors: {
  primary: '#E8F0FE', secondary: '#4A72D4', accent: '#F5A623',
  background: '#0D0D0F', surface: '#161618', 'surface-2': '#1E1E21',
  border: '#2A2A30', 'text-primary': '#F0F0F2', 'text-secondary': '#7A7A85',
  success: '#3ECF8E', warning: '#F5A623', error: '#E84040',
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

1. Dark mode only. Background #0D0D0F for pages, Surface #161618 for cards, Surface 2 #1E1E21 for nested elements. Never introduce light backgrounds.
2. Inter for all headings and body. JetBrains Mono for all code, commands, IDs, paths, durations, and any technical string.
3. Pipeline/build status always uses the defined status color system — Queued/Running/Passed/Failed/Cancelled. Never improvise status colors.
4. Motion: 100–180ms, instant feel. No page transition animations. No skeleton loaders where data can load fast.
5. Compact density. 16px card padding, 32px button height. Never over-space.
6. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
7. When in doubt: would a developer using this at 2am during an incident find it clear and fast? If not, remove visual complexity until it is.
