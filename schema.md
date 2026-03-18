# brandpack.md — Output Schema

Strict scope: **visual design tokens only**. No copy direction, no content rules, no UX flows.

Output a single complete file. Start with `# Brand:`. No preamble, no explanation, no markdown fences wrapping the output.

---

# Brand: [Name]
> [One line: what it is + the visual feeling it should create]

---

## Visual Identity

**Aesthetic:** [2–3 words: e.g. "warm minimalism", "dark precision", "institutional authority"]
**Mode:** [Light / Dark / Both]
**References:** [2–3 real products or design movements with similar visual language]
**Never look like:** [2 things this brand must never visually resemble]

---

## Colors

Primary: #XXXXXX — [usage: CTAs, active states, key UI elements]
Secondary: #XXXXXX — [usage]
Accent: #XXXXXX — [usage — note if used sparingly]
Background: #XXXXXX — [page background]
Surface: #XXXXXX — [cards, panels, modals]
Border: #XXXXXX — [dividers, input borders, table lines]
Text Primary: #XXXXXX — [headings, body]
Text Secondary: #XXXXXX — [captions, metadata, placeholders]
Success: #XXXXXX
Warning: #XXXXXX
Error: #XXXXXX

[Add domain-specific colors only when the product genuinely requires them]

Rules:
- [Usage rule 1]
- [Usage rule 2]
- [Usage rule 3]

---

## Typography

Heading: [Font name] — [Google Fonts URL]
Why: [One sentence tied to this specific audience and product]

Body: [Font name] — [Google Fonts URL]
Why: [One sentence]

Mono: [Font name] — [Google Fonts URL]
For: [What data or content uses mono in this product]

Scale:
- Display: [px] / [weight] — hero only
- H1: [px] / [weight]
- H2: [px] / [weight]
- H3: [px] / [weight]
- Body: [px] / 400 / line-height [ratio]
- Body SM: [px] / 400
- Label: [px] / [weight] — [case convention]
- Data: [px] / [weight] — mono font

Rules:
- [e.g. "Headings always sentence case"]
- [e.g. "All numerical data in mono font, no exceptions"]

---

## Spacing & Layout

Base unit: [4px or 8px]
Scale: [list values]
Max width: [px]
Grid: [columns, gutter]
Density: [compact / default / spacious] — [one sentence why]

---

## Border Radius

sm: [px] — [usage]
md: [px] — [usage]
lg: [px] — [usage]
full: 9999px — [note if this brand uses or avoids pill shapes]

Personality: [One sentence — what the radius choices say about this brand]

---

## Components

Buttons:
- Primary: [bg, text color, radius, hover behavior]
- Secondary: [style]
- Ghost: [style]
- Rules: [brand-specific constraints, e.g. "no shadows ever"]

Cards:
- [bg, border, radius, shadow or not, padding]
- Hover: [behavior if interactive]

Inputs:
- [border, radius, focus state, error state]

Navigation:
- [style, active state]

Icons:
- [Preferred set — Lucide / Heroicons / Phosphor]
- [Size and stroke conventions]

---

## Motion

Personality: [One sentence]
Default: [duration + easing for micro] / [duration + easing for layout]
Hover: [specific description]
Never: [explicit list of banned effects]

---

## Code

### CSS Variables

```css
:root {
  --color-primary: #XXXXXX;
  --color-secondary: #XXXXXX;
  --color-accent: #XXXXXX;
  --color-background: #XXXXXX;
  --color-surface: #XXXXXX;
  --color-border: #XXXXXX;
  --color-text-primary: #XXXXXX;
  --color-text-secondary: #XXXXXX;
  --color-success: #XXXXXX;
  --color-warning: #XXXXXX;
  --color-error: #XXXXXX;

  --font-heading: '[Font]', [fallback];
  --font-body: '[Font]', [fallback];
  --font-mono: '[Font]', [fallback];

  --space-1: Xpx; --space-2: Xpx; --space-3: Xpx; --space-4: Xpx;
  --space-6: Xpx; --space-8: Xpx; --space-12: Xpx; --space-16: Xpx;

  --radius-sm: Xpx; --radius-md: Xpx; --radius-lg: Xpx; --radius-full: 9999px;

  --transition-fast: Xms ease-out;
  --transition-base: Xms ease-in-out;
}
```

### Tailwind Extension

```js
// tailwind.config.js — extend
colors: {
  primary: '#XXXXXX', secondary: '#XXXXXX', accent: '#XXXXXX',
  background: '#XXXXXX', surface: '#XXXXXX', border: '#XXXXXX',
  'text-primary': '#XXXXXX', 'text-secondary': '#XXXXXX',
  success: '#XXXXXX', warning: '#XXXXXX', error: '#XXXXXX',
},
fontFamily: {
  heading: ['"[Font]"', '[fallback]'],
  body: ['[Font]', '[fallback]'],
  mono: ['"[Font]"', '[fallback]'],
},
borderRadius: { sm: 'Xpx', md: 'Xpx', lg: 'Xpx' },
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="[complete Google Fonts URL]" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. Use only the colors defined above. Never introduce new colors.
2. Use only the fonts defined above. Never default to Inter, Roboto, or system fonts unless defined here.
3. Apply border radius tokens per the radius personality.
4. Apply motion rules — if an effect is banned, it does not appear anywhere.
5. Apply component rules literally — buttons, cards, inputs match these specs exactly.
6. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
7. When in doubt: does this look like [aesthetic from Visual Identity]? If not, adjust until it does.
