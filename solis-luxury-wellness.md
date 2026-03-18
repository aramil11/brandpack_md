# Brand: Solis
> A premium wellness membership for people who treat recovery as seriously as performance — restrained, elevated, unhurried.

---

## Visual Identity

**Aesthetic:** Quiet luxury
**Mode:** Light
**References:** Aesop (restraint, ritual, premium materiality), Winsome (editorial wellness), Eight Sleep (performance + premium minimalism)
**Never look like:** A gym chain (loud, aggressive, discount-driven). A mass-market wellness app (gamified, badge-heavy, motivational-poster tone).

---

## Colors

Primary: #1A1A18 — near-black, primary actions, headings, key elements
Secondary: #3D3D3A — depth, secondary text, supporting UI
Accent: #B5924A — warm gold, used only for premium tier markers and key highlights
Background: #FAF9F6 — warm near-white, primary page surface
Surface: #F2F0EB — cards, panels, modals
Border: #E4E0D8 — all dividers, input borders
Text Primary: #1A1A18 — headings, body
Text Secondary: #8A8780 — captions, metadata, secondary labels
Success: #4A7C5F — confirmed, completed
Warning: #9B7A2E — attention
Error: #8B3030 — errors

Rules:
- Accent gold appears only for membership tier markers and premium feature indicators. Never decorative.
- Never introduce bright colors. The palette is deliberately narrow — restraint is the brand.
- Background is never pure white. Warmth is non-negotiable.

---

## Typography

Heading: Cormorant Garamond — https://fonts.google.com/specimen/Cormorant+Garamond
Why: High-contrast editorial serif signals luxury and restraint; the thin strokes and classical proportions position this above mass-market wellness without feeling medical.

Body: Jost — https://fonts.google.com/specimen/Jost
Why: Geometric sans with elegant proportions; pairs with Cormorant without competing; legible at small sizes for content-heavy wellness guides.

Mono: IBM Plex Mono — https://fonts.google.com/specimen/IBM+Plex+Mono
For: Biometric data, session durations, measurement values.

Scale:
- Display: 64px / 300 — light weight intentional; luxury brands don't shout
- H1: 44px / 400
- H2: 30px / 400
- H3: 20px / 500
- Body: 16px / 400 / line-height 1.75
- Body SM: 14px / 400
- Label: 10px / 500 — uppercase, letter-spacing 0.12em
- Data: 15px / 400 — mono font

Rules:
- Cormorant Garamond always sentence case — never uppercase headings
- Body line height deliberately generous (1.75) — this content is read slowly and thoughtfully
- Labels always uppercase with wide tracking — the only uppercase permitted

---

## Spacing & Layout

Base unit: 8px
Scale: 8, 16, 24, 40, 64, 96, 128, 160
Max width: 1080px
Grid: 12-column, 40px gutter
Density: Spacious — generous whitespace is the primary luxury signal; every section breathes

---

## Border Radius

sm: 2px — inputs, data cells
md: 4px — cards, buttons
lg: 8px — modals, panels
full: 9999px — avoid entirely

Personality: Nearly square. Luxury brands don't round their edges — restraint extends to geometry.

---

## Components

Buttons:
- Primary: #1A1A18 background, #FAF9F6 text, 4px radius, no shadow, hover: lighten to #3D3D3A
- Secondary: transparent, #1A1A18 border 1px, #1A1A18 text, hover: Surface background
- Ghost: Text Secondary, no border, Text Primary on hover — for tertiary actions only
- Rules: No gradients. No shadows. Never rounded beyond 4px. Generous padding (20px horizontal).

Cards:
- Surface background (#F2F0EB), Border 1px, 4px radius, 40px padding, no shadow
- Hover: border shifts to #C8C4BC — no lift, no shadow, no translate

Inputs:
- Surface background, Border 1px, 2px radius, Text Primary
- Focus: Text Primary border 2px, no glow ring
- Placeholder: Text Secondary

Navigation:
- Top nav, Background color, bottom border 1px
- Active: Text Primary, 1px underline offset 4px
- Inactive: Text Secondary

Icons:
- Phosphor Icons, Thin weight (unique to this brand — reinforces the luxury lightness)
- 20px default, 24px for feature callouts
- Text Secondary default

---

## Motion

Personality: Slow and deliberate — every transition should feel like exhaling; users are here to slow down, not be stimulated.
Default: 300ms ease-out for micro / 500ms ease-in-out for reveals and page transitions
Hover: Border shifts 300ms. Text color shifts 200ms. Nothing else.
Never: Bounce. Snap. Flash. Fast transitions under 200ms. Anything with kinetic energy. Parallax. Auto-scroll.

---

## Code

### CSS Variables

```css
:root {
  --color-primary: #1A1A18;
  --color-secondary: #3D3D3A;
  --color-accent: #B5924A;
  --color-background: #FAF9F6;
  --color-surface: #F2F0EB;
  --color-border: #E4E0D8;
  --color-text-primary: #1A1A18;
  --color-text-secondary: #8A8780;
  --color-success: #4A7C5F;
  --color-warning: #9B7A2E;
  --color-error: #8B3030;

  --font-heading: 'Cormorant Garamond', Georgia, serif;
  --font-body: 'Jost', system-ui, sans-serif;
  --font-mono: 'IBM Plex Mono', 'Courier New', monospace;

  --space-1: 8px; --space-2: 16px; --space-3: 24px; --space-4: 40px;
  --space-6: 64px; --space-8: 96px; --space-12: 128px; --space-16: 160px;

  --radius-sm: 2px; --radius-md: 4px; --radius-lg: 8px; --radius-full: 9999px;

  --transition-fast: 300ms ease-out;
  --transition-base: 500ms ease-in-out;
}
```

### Tailwind Extension

```js
colors: {
  primary: '#1A1A18', secondary: '#3D3D3A', accent: '#B5924A',
  background: '#FAF9F6', surface: '#F2F0EB', border: '#E4E0D8',
  'text-primary': '#1A1A18', 'text-secondary': '#8A8780',
  success: '#4A7C5F', warning: '#9B7A2E', error: '#8B3030',
},
fontFamily: {
  heading: ['"Cormorant Garamond"', 'Georgia', 'serif'],
  body: ['Jost', 'system-ui', 'sans-serif'],
  mono: ['"IBM Plex Mono"', '"Courier New"', 'monospace'],
},
borderRadius: { sm: '2px', md: '4px', lg: '8px' },
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500&family=Jost:wght@400;500&family=IBM+Plex+Mono:wght@400&display=swap" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. Use only the colors defined above. The palette is intentionally narrow — never introduce new colors.
2. Cormorant Garamond for all headings, always sentence case. Jost for all body. IBM Plex Mono for biometric data and measurements only.
3. Spacing is generous. Do not compress sections. Whitespace is the product.
4. Motion is slow: 300–500ms. No transitions under 200ms. Nothing kinetic or energetic.
5. Nearly square radius throughout. Never pill shapes.
6. Accent gold for premium indicators only — never decorative.
7. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
8. When in doubt: does this feel like a luxury spa designed by an architect? If it feels like a fitness app, remove color and energy until it doesn't.
