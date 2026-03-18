# Brand: Vault
> A personal finance app for people who want to understand their money, not just track it — calm, intelligent, never preachy.

---

## Visual Identity

**Aesthetic:** Warm financial clarity
**Mode:** Light (dark mode optional)
**References:** Linear (clean, confident SaaS), Monzo (approachable finance), Stripe's documentation (structured, trustworthy)
**Never look like:** A traditional bank portal (cold, cluttered, 2009). A crypto dashboard (dark, aggressive, hype-driven).

---

## Colors

Primary: #2D6A4F — deep muted green, CTAs, active states, key actions
Secondary: #1B4332 — nav anchors, footer, depth elements
Accent: #D4A853 — key financial highlights, net positive indicators, used sparingly
Background: #F8F6F2 — warm off-white, never stark white
Surface: #EFECE6 — cards, panels, input backgrounds
Border: #DDD9D1 — dividers, table lines, input borders
Text Primary: #1C1C1A — headings, body
Text Secondary: #6B6760 — captions, metadata, secondary values
Success: #40916C — positive balance, income, growth
Warning: #C47C1B — attention required, approaching limits
Error: #9B3B2E — negative balance, overspend, failed actions

Rules:
- Accent gold appears only on net positive financial moments — never decoratively
- Green primary is the only action color. Never use red/orange as primary
- Background and Surface must not be pure white — warmth signals approachability, not anxiety

---

## Typography

Heading: DM Serif Display — https://fonts.google.com/specimen/DM+Serif+Display
Why: Serif warmth signals trustworthiness and permanence without the coldness of banking; feels like a knowledgeable friend, not a financial institution.

Body: DM Sans — https://fonts.google.com/specimen/DM+Sans
Why: Matched family to DM Serif; highly legible at small sizes for data-dense financial views, slightly rounded terminals keep the tone approachable.

Mono: JetBrains Mono — https://fonts.google.com/specimen/JetBrains+Mono
For: All currency amounts, account numbers, percentage values, transaction IDs.

Scale:
- Display: 48px / 700 — hero balance display only
- H1: 34px / 700
- H2: 24px / 600
- H3: 18px / 600
- Body: 15px / 400 / line-height 1.65
- Body SM: 13px / 400
- Label: 11px / 600 — uppercase, letter-spacing 0.06em
- Data: 20px / 600 — mono font, for primary financial figures

Rules:
- All currency values in JetBrains Mono, no exceptions
- DM Serif Display headings always sentence case — never uppercase
- Financial figures larger than surrounding text; the number is always the hero

---

## Spacing & Layout

Base unit: 8px
Scale: 8, 16, 24, 32, 48, 64, 96
Max width: 1120px
Grid: 12-column, 24px gutter
Density: Default — financial data needs breathing room; users pause to understand, not scan and leave

---

## Border Radius

sm: 6px — input fields, small badges, transaction rows
md: 12px — cards, buttons, chart containers
lg: 20px — modals, account panels
full: 9999px — balance pills, category chips (used intentionally)

Personality: Gently rounded — approachable and modern without feeling like a toy; this is friendly finance, not a game.

---

## Components

Buttons:
- Primary: #2D6A4F background, #F8F6F2 text, 12px radius, no shadow, hover: darken 8%
- Secondary: transparent, #2D6A4F border 1.5px, #2D6A4F text, hover: Surface background
- Ghost: Text Primary color, no border, underline on hover
- Rules: No gradients. No drop shadows. Minimum 44px height.

Cards:
- Surface background (#EFECE6), Border 1px, 12px radius, 24px padding, no shadow
- Transaction cards: left border 3px in category color (muted, defined per category)
- Hover: border shifts to #C8C4BC, no lift

Inputs:
- Surface background, Border 1px, 6px radius
- Focus: Primary border 2px, no glow
- Error: Error color border + small error label below

Navigation:
- Left sidebar on desktop, bottom tab bar on mobile
- Active: Primary left border 3px + Primary text
- Inactive: Text Secondary

Icons:
- Lucide Icons, 1.5px stroke
- 18px inline, 22px standalone
- Category icons in muted accent tones, utility icons in Text Secondary

---

## Motion

Personality: Smooth and reassuring — motion should feel like water, never a jolt; users are often checking anxiety-inducing information.
Default: 200ms ease-out for micro / 320ms ease-in-out for screen transitions
Hover: Cards shift border color 200ms. Buttons darken 150ms. Nothing lifts or jumps.
Never: Celebration animations on spending. Bounce. Flash. Anything that feels alarming when a number changes.

---

## Code

### CSS Variables

```css
:root {
  --color-primary: #2D6A4F;
  --color-secondary: #1B4332;
  --color-accent: #D4A853;
  --color-background: #F8F6F2;
  --color-surface: #EFECE6;
  --color-border: #DDD9D1;
  --color-text-primary: #1C1C1A;
  --color-text-secondary: #6B6760;
  --color-success: #40916C;
  --color-warning: #C47C1B;
  --color-error: #9B3B2E;

  --font-heading: 'DM Serif Display', Georgia, serif;
  --font-body: 'DM Sans', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;

  --space-1: 8px; --space-2: 16px; --space-3: 24px; --space-4: 32px;
  --space-6: 48px; --space-8: 64px; --space-12: 96px;

  --radius-sm: 6px; --radius-md: 12px; --radius-lg: 20px; --radius-full: 9999px;

  --transition-fast: 200ms ease-out;
  --transition-base: 320ms ease-in-out;
}
```

### Tailwind Extension

```js
colors: {
  primary: '#2D6A4F', secondary: '#1B4332', accent: '#D4A853',
  background: '#F8F6F2', surface: '#EFECE6', border: '#DDD9D1',
  'text-primary': '#1C1C1A', 'text-secondary': '#6B6760',
  success: '#40916C', warning: '#C47C1B', error: '#9B3B2E',
},
fontFamily: {
  heading: ['"DM Serif Display"', 'Georgia', 'serif'],
  body: ['"DM Sans"', 'system-ui', 'sans-serif'],
  mono: ['"JetBrains Mono"', '"Courier New"', 'monospace'],
},
borderRadius: { sm: '6px', md: '12px', lg: '20px' },
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. Use only the colors defined above. Never introduce new colors. Never use pure white (#FFFFFF) — use Background.
2. DM Serif Display for all headings. DM Sans for all body. JetBrains Mono for every currency value, percentage, and financial figure — no exceptions.
3. Border radius: moderately rounded throughout. Never sharp corners, never full pills except for category chips.
4. Motion: smooth and calm. 200–320ms. Nothing alarming, nothing celebratory around financial data.
5. Buttons: flat, no shadows, no gradients. Green primary only.
6. Accent gold is for net positive financial moments only — never decorative.
7. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
8. When in doubt: does this feel like a calm, knowledgeable friend helping with money — not a bank, not a trading app? If not, simplify.
