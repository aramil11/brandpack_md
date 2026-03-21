# brandpack.md — Output Schema

Strict scope: **visual design tokens only**. No copy direction, no content rules, no UX flows.

Output a single complete file. Start with `# Brand:`. No preamble, no explanation, no markdown fences wrapping the output.

---

# Brand: [Name]
> [One line: what it is + the visual feeling it should create]

**Source:** [Brief / Website / Repo / combination] — [one sentence on what was extracted or inferred]

---

## Visual Identity

**Aesthetic:** [2–3 words]
**Mode:** [Light / Dark / Both]
**References:** [2–3 real products or design movements with similar visual language]
**Never look like:** [2 things this brand must never visually resemble]

---

## Colors

[For each color, use one of these annotation formats:]
[Extracted from source:] Primary: #XXXXXX — [source: tailwind.config / globals.css / component] — [usage]
[Inferred or added:]     Primary: #XXXXXX — [inferred: reason] — [usage]

Primary: #XXXXXX — [source or inferred note] — [usage: CTAs, active states, key UI elements]
Secondary: #XXXXXX — [source or inferred] — [usage]
Accent: #XXXXXX — [source or inferred] — [usage, note if used sparingly]
Background: #XXXXXX — [source or inferred] — [page background]
Surface: #XXXXXX — [source or inferred] — [cards, panels, modals]
Border: #XXXXXX — [source or inferred] — [dividers, input borders, table lines]
Text Primary: #XXXXXX — [source or inferred] — [headings, body]
Text Secondary: #XXXXXX — [source or inferred] — [captions, metadata, placeholders]
Success: #XXXXXX
Warning: #XXXXXX
Error: #XXXXXX

[Add domain-specific colors only when the product genuinely requires them]

Rules:
- [Usage rule 1]
- [Usage rule 2]
- [Usage rule 3]

[If repo input and inconsistencies found:]
Resolved inconsistencies:
- [e.g. "Three different grey values in use (#888, #8A8A8A, #909090) — standardized to Text Secondary: #8A8A8A"]
- [e.g. "Primary button used #2563EB in desktop and #3B82F6 on mobile — standardized to #2563EB throughout"]

---

## Typography

Heading: [Font name] — [Google Fonts URL]
Source: [extracted from / inferred]
Why: [One sentence tied to this specific audience and product]

Body: [Font name] — [Google Fonts URL]
Source: [extracted from / inferred]
Why: [One sentence]

Mono: [Font name] — [Google Fonts URL]
Source: [extracted from / inferred]
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

[Resolved inconsistencies if any]

---

## Spacing & Layout

Base unit: [4px or 8px]
Scale: [list values]
Max width: [px]
Grid: [columns, gutter]
Density: [compact / default / spacious] — [one sentence why]

[Resolved inconsistencies if any]

---

## Border Radius

sm: [px] — [usage]
md: [px] — [usage]
lg: [px] — [usage]
full: 9999px — [note if this brand uses or avoids pill shapes]

Personality: [One sentence]

[Resolved inconsistencies if any]

---

## Components

Buttons:
- Primary: [bg, text color, radius, hover behavior]
- Secondary: [style]
- Ghost: [style]
- Rules: [brand-specific constraints]

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

[Resolved inconsistencies if any]

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
6. [For repo-sourced brandpacks:] This file is the source of truth for the entire codebase. Existing code that contradicts it should be updated to match, not the other way around.
7. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
8. When in doubt: does this look like [aesthetic from Visual Identity]? If not, adjust until it does.
