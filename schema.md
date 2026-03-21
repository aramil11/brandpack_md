# brandpack.md — Output Schema

Strict scope: **visual design tokens only**. No copy direction, no content rules, no UX flows.

Output a single complete file starting with `# Brand:`. No preamble, no fences wrapping the entire output.

For repo-sourced brandpacks, annotate each token with its source:
`[extracted: tailwind.config]` or `[inferred: no background token found]`

---

# Brand: [Name]
> [One line: what it is + the precise visual feeling it creates]

**Source:** [Brief / URL / Repo / combination — what was extracted vs inferred]

---

## Visual Identity

**Aesthetic:** [2–4 words: e.g. "warm financial clarity", "dark precision", "quiet institutional authority", "playful warm utility"]
**Mode:** [Light / Dark / Both — with rationale]
**References:** [2–3 real products or design movements with genuinely similar visual language — be specific, not generic]
**Never look like:** [2–3 things this brand must never visually resemble — derived from audience reasoning]

---

## Colors

[For repo input, annotate source. For brief/URL input, omit annotations.]

Primary: #XXXXXX — [evocative name] — [usage: CTAs, active states, key interactive elements]
Secondary: #XXXXXX — [evocative name] — [usage]
Accent: #XXXXXX — [evocative name] — [usage — always note if used sparingly and why]
Background: #XXXXXX — [evocative name] — [page background — never pure #FFFFFF]
Surface: #XXXXXX — [evocative name] — [cards, panels, modals]
Surface Raised: #XXXXXX — [evocative name] — [elevated cards, dropdowns, tooltips]
Border: #XXXXXX — [evocative name] — [dividers, input borders, table lines]
Text Primary: #XXXXXX — [evocative name] — [headings, body — never pure #000000]
Text Secondary: #XXXXXX — [evocative name] — [captions, metadata, placeholders]
Text Disabled: #XXXXXX — [evocative name] — [disabled states, hints]
Success: #XXXXXX — [evocative name]
Warning: #XXXXXX — [evocative name]
Error: #XXXXXX — [evocative name]
Info: #XXXXXX — [evocative name]

[Add domain-specific colors only when genuinely required — e.g. status tiers, chart series, zone colors]

**Color psychology:**
[2–3 sentences explaining WHY this palette works for this specific audience — not generic color theory,
but the actual reasoning: this shade of green signals X to Y audience because Z]

**Color rules:**
- [Usage rule 1 — e.g. "Accent used only for X, never as a general background"]
- [Usage rule 2]
- [Usage rule 3]

**Dark mode overrides:** [yes / no]
[If yes — provide the full token override set:]
Background (dark): #XXXXXX — [note: not an inversion — deliberate dark surface]
Surface (dark): #XXXXXX — [lighter than background for elevation]
Surface Raised (dark): #XXXXXX — [elevation expressed through lightness, not shadow]
Text Primary (dark): #XXXXXX — [off-white, not pure white — reduces glare]
Text Secondary (dark): #XXXXXX
Border (dark): #XXXXXX — [subtle, low contrast]
Primary (dark): #XXXXXX — [slightly desaturated vs light mode — vivid colors look harsh on dark]

---

## Typography

Heading: [Font name] — [Google Fonts URL]
Why: [One sentence tied to THIS specific audience and product — not generic praise]

Body: [Font name] — [Google Fonts URL]
Why: [One sentence — why this pairs with the heading font and serves this use case]

Mono: [Font name] — [Google Fonts URL]
For: [What data or content uses mono — technical strings, financial figures, timestamps, etc.]

**Type scale:**
- Display: [px] / [weight] / line-height [ratio] — hero only, use sparingly
- H1: [px] / [weight] / [ratio]
- H2: [px] / [weight] / [ratio]
- H3: [px] / [weight] / [ratio]
- H4: [px] / [weight] / [ratio]
- Body LG: [px] / 400 / [ratio] — lead paragraphs
- Body: [px] / 400 / [ratio] — default
- Body SM: [px] / 400 / [ratio] — captions, metadata
- Label: [px] / [weight] / [ratio] — [case convention: sentence / uppercase + tracked]
- Code: [px] / [weight] — mono font

**Typography rules:**
- [e.g. "Headings always sentence case — uppercase reserved for label tokens only"]
- [e.g. "All financial/technical values in mono font, no exceptions"]
- [e.g. "Body line-height deliberately generous at 1.7 — users read carefully in this context"]

---

## Spacing & Layout

Base unit: [4px or 8px — with reasoning: why this base for this product type]
Scale: [explicit list — e.g. 4, 8, 12, 16, 24, 32, 48, 64, 96, 128]
Max content width: [px]
Grid: [columns, gutter — e.g. "12-column, 24px gutter"]
Density: [compact / default / spacious] — [one sentence why this density fits this audience]

---

## Border Radius

sm: [px] — [usage: inputs, small badges]
md: [px] — [usage: buttons, cards]
lg: [px] — [usage: modals, large panels]
full: 9999px — [note whether this brand uses pill shapes or avoids them, and why]

**Radius personality:** [One sentence — what the radius choices communicate about this brand]

---

## Shadows & Elevation

[Shadows communicate depth and hierarchy. Skip entirely if this brand is flat by design — state that explicitly.]

sm: [CSS box-shadow value] — [usage: subtle card lift, hover state]
md: [CSS box-shadow value] — [usage: dropdowns, modals, standard cards]
lg: [CSS box-shadow value] — [usage: side panels, dialogs, prominent UI]
xl: [CSS box-shadow value] — [usage: max elevation, temporary overlays]

**Shadow personality:** [One sentence — e.g. "Warm-tinted shadows (slight amber cast) reinforce the brand's warmth rather than using cold gray defaults"]
**Shadow rules:**
- [e.g. "No shadows on buttons — flatness signals confidence for this brand"]
- [e.g. "Dark mode uses elevation-through-lightness, not shadows"]

---

## Motion & Animation

**Personality:** [One sentence — the overall feel: e.g. "Slow and deliberate, like turning a page"; "Fast and snappy — zero perceived latency"; "Warm and bouncy — motion celebrates progress"]

**Durations:**
- Instant: 80ms — micro-feedback (button press, toggle)
- Fast: 150ms — hover states, small UI changes
- Base: 250ms — transitions, reveals
- Slow: 400ms — page transitions, complex layouts
- [Add or remove tiers as appropriate for this product]

**Easing:**
- Enter: ease-out — elements arrive decisively
- Exit: ease-in — elements depart quietly
- Move: ease-in-out — elements reposition smoothly
- [Override if brand personality requires something specific — e.g. spring for playful products]

**Named transitions:**
- transition-hover: [duration + easing for hover states]
- transition-enter: [duration + easing for content entering the viewport]
- transition-exit: [duration + easing for content leaving]
- transition-layout: [duration + easing for layout changes]

**Never:**
[Explicit list of banned effects — e.g. "No bounce/elastic (signals consumer, not professional)", "No parallax", "No autoplay video", "No celebration animations on serious actions"]

**prefers-reduced-motion:** [how this brand handles reduced motion — e.g. "All transitions collapse to instant, decorative animations disabled"]

---

## Components

**Buttons:**
- Primary: [bg, text, border, radius, padding, hover behavior — specific values]
- Secondary: [style]
- Ghost/Outline: [style]
- Destructive: [style]
- Disabled: [style — opacity level, cursor]
- Rules: [brand-specific constraints, e.g. "No gradients", "No drop shadows", "Min 44px touch target"]

**Cards:**
- Default: [bg, border, radius, shadow, padding]
- Interactive: [hover behavior — specific transition]
- [Variant if relevant — e.g. feature card, data card, list item]

**Inputs:**
- Default: [border, radius, bg, text, padding]
- Focus: [border color, focus ring — specify if glow or clean border]
- Error: [border color, error message style]
- Disabled: [opacity, cursor]

**Navigation:**
- Style: [top nav / left sidebar / bottom tabs — and why]
- Active state: [specific visual treatment]
- Mobile behavior: [how it collapses or adapts]

**Badges & Labels:**
- Default: [style]
- Status variants: [how success/warning/error/info map to badge styles]

**Icons:**
- Set: [Lucide / Heroicons / Phosphor / Tabler — with specific reasoning]
- Style: [outline / filled / duotone — consistent across the product]
- Size: [default sizes at different contexts — 16px inline, 20px standalone, 24px feature]
- Weight: [stroke width if applicable]

---

## Code

### CSS Variables

```css
:root {
  /* ── Colors ──────────────────────────────────────── */
  --color-primary: #XXXXXX;
  --color-secondary: #XXXXXX;
  --color-accent: #XXXXXX;
  --color-background: #XXXXXX;
  --color-surface: #XXXXXX;
  --color-surface-raised: #XXXXXX;
  --color-border: #XXXXXX;
  --color-text-primary: #XXXXXX;
  --color-text-secondary: #XXXXXX;
  --color-text-disabled: #XXXXXX;
  --color-success: #XXXXXX;
  --color-warning: #XXXXXX;
  --color-error: #XXXXXX;
  --color-info: #XXXXXX;

  /* ── Typography ──────────────────────────────────── */
  --font-heading: '[Font]', [fallback];
  --font-body: '[Font]', [fallback];
  --font-mono: '[Font]', [fallback];

  /* ── Type Scale ──────────────────────────────────── */
  --text-display: [px];
  --text-h1: [px];
  --text-h2: [px];
  --text-h3: [px];
  --text-h4: [px];
  --text-body-lg: [px];
  --text-body: [px];
  --text-body-sm: [px];
  --text-label: [px];
  --text-code: [px];

  /* ── Spacing ─────────────────────────────────────── */
  --space-1: Xpx;
  --space-2: Xpx;
  --space-3: Xpx;
  --space-4: Xpx;
  --space-6: Xpx;
  --space-8: Xpx;
  --space-12: Xpx;
  --space-16: Xpx;
  --space-24: Xpx;

  /* ── Radius ──────────────────────────────────────── */
  --radius-sm: Xpx;
  --radius-md: Xpx;
  --radius-lg: Xpx;
  --radius-full: 9999px;

  /* ── Shadows ─────────────────────────────────────── */
  --shadow-sm: [CSS value];
  --shadow-md: [CSS value];
  --shadow-lg: [CSS value];
  --shadow-xl: [CSS value];

  /* ── Motion ──────────────────────────────────────── */
  --duration-instant: 80ms;
  --duration-fast: 150ms;
  --duration-base: 250ms;
  --duration-slow: 400ms;
  --ease-enter: ease-out;
  --ease-exit: ease-in;
  --ease-move: ease-in-out;
  --transition-hover: Xms ease-out;
  --transition-enter: Xms ease-out;
  --transition-layout: Xms ease-in-out;
}
```

### Tailwind Extension

```js
// tailwind.config.js — extend section
colors: {
  primary: '#XXXXXX',
  secondary: '#XXXXXX',
  accent: '#XXXXXX',
  background: '#XXXXXX',
  surface: '#XXXXXX',
  'surface-raised': '#XXXXXX',
  border: '#XXXXXX',
  'text-primary': '#XXXXXX',
  'text-secondary': '#XXXXXX',
  'text-disabled': '#XXXXXX',
  success: '#XXXXXX',
  warning: '#XXXXXX',
  error: '#XXXXXX',
  info: '#XXXXXX',
},
fontFamily: {
  heading: ['"[Font]"', '[fallback]'],
  body: ['[Font]', '[fallback]'],
  mono: ['"[Font]"', '[fallback]'],
},
borderRadius: {
  sm: 'Xpx', md: 'Xpx', lg: 'Xpx',
},
boxShadow: {
  sm: '[CSS value]',
  md: '[CSS value]',
  lg: '[CSS value]',
  xl: '[CSS value]',
},
transitionDuration: {
  instant: '80ms', fast: '150ms', base: '250ms', slow: '400ms',
},
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="[complete Google Fonts URL with all weights]" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context, follow these rules for every UI component:

1. **Colors:** Use only the defined palette. Never introduce new colors. Never use pure `#FFFFFF` or `#000000` — use Background and Text Primary tokens.
2. **Typography:** [Heading font] for all headings. [Body font] for body. [Mono font] for [specific use case]. Never default to Inter, Roboto, or system fonts unless defined here.
3. **Spacing:** Use only values from the spacing scale. No arbitrary pixel values.
4. **Radius:** Apply per the radius personality. [Specific constraint — e.g. "Never pill shapes" or "Pill shapes only for status badges"].
5. **Shadows:** [Specific shadow rule for this brand — e.g. "Use shadow-md for cards, no shadows on buttons"].
6. **Motion:** [Specific motion rule — e.g. "All transitions use transition-hover for interactive states. Nothing slower than duration-slow"].
7. **Components:** Buttons, cards, inputs follow the component specs exactly.
8. **Dark mode:** [If yes: "Apply dark mode overrides when prefers-color-scheme: dark or data-theme='dark'". If no: "Light mode only — do not implement dark mode variants"].
9. **Scope:** This file controls visuals only. Do NOT change copy, content, features, or UX structure.
10. **Archetype check:** Before finalizing any component — does this look like [aesthetic from Visual Identity]? If it looks like a generic SaaS template, simplify and apply the brand tokens more deliberately.

[Add any brand-specific rules that don't fit the above — max 3 additional rules]
