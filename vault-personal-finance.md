# Brand: Vault
> A personal finance app for people who want to understand their money, not just track it — calm, intelligent, never preachy.

**Source:** Brief — all tokens inferred from product description and audience reasoning.

---

## Visual Identity

**Aesthetic:** Warm financial clarity
**Mode:** Light (dark mode supported — overrides below)
**References:** Linear's dashboard density + Monzo's approachability + Stripe's typographic restraint
**Never look like:** A traditional bank portal (cold, grey, clinical 2010 web). A crypto trading app (dark, aggressive, hype-driven). A diet/wellness tracker (progress bars, gamification, judgment).

---

## Colors

Primary: #2D6A4F — Forest — CTAs, active states, interactive elements, focus rings
Secondary: #1B4332 — Deep Forest — nav anchors, high-emphasis text, section dividers
Accent: #D4A853 — Harvest Gold — net positive indicators, key financial milestones, used sparingly
Background: #F8F6F2 — Parchment — page background; warm off-white signals approachability, not clinical white
Surface: #EFECE6 — Linen — cards, panels, input backgrounds
Surface Raised: #E8E3DC — Warm Stone — elevated cards, dropdowns, tooltips, popovers
Border: #DDD9D1 — Sand — dividers, input borders, table lines
Text Primary: #1C1C1A — Near Black — headings, body; warm undertone, not pure black
Text Secondary: #6B6760 — Warm Dusk — captions, metadata, secondary labels
Text Disabled: #A8A49F — Warm Mist — disabled states and placeholder text
Success: #40916C — Sage — income, positive balance, confirmed states
Warning: #C47C1B — Amber — approaching budget limits, attention needed
Error: #9B3B2E — Brick — overspend, failed transactions, error states
Info: #3A72A8 — Slate Blue — informational, neutral alerts

**Color psychology:**
Muted forest green as primary avoids the "financial institution navy" cliché while retaining trustworthiness — it reads as growth and calm rather than corporate. The warm off-white background is critical: it evokes paper and notebooks rather than a dashboard, signalling this tool is personal and caring rather than analytical and judging. Harvest Gold is used only for positive financial moments because money should feel meaningful, not gamified.

**Color rules:**
- Accent gold never appears on negative or neutral states — only genuine achievements and positive balances
- Never pure white (#FFFFFF) — always use Parchment or warmer surfaces
- Primary green and Brick red must never appear adjacent in equal weight — one must clearly dominate

**Dark mode overrides:** yes
Background (dark): #161614 — very dark warm neutral, not pure black
Surface (dark): #1E1D1A — slightly lighter, first elevation tier
Surface Raised (dark): #262420 — second elevation tier (dropdowns, popovers)
Text Primary (dark): #E8E4DE — warm off-white, not pure white — reduces eye strain
Text Secondary (dark): #9A9690 — muted warm grey
Border (dark): #2E2C28 — subtle warm border
Primary (dark): #3D8C68 — slightly brighter in dark mode for visibility
Accent (dark): #C4962A — slightly desaturated gold

---

## Typography

Heading: DM Serif Display — https://fonts.google.com/specimen/DM+Serif+Display
Why: Serif warmth signals trustworthiness and permanence — reads like a knowledgeable friend, not a financial institution; elegant without being stuffy.

Body: DM Sans — https://fonts.google.com/specimen/DM+Sans
Why: Matched family for visual cohesion; highly legible at small sizes for data-dense financial views; rounded terminals keep tone approachable without being playful.

Mono: JetBrains Mono — https://fonts.google.com/specimen/JetBrains+Mono
For: All currency amounts, account numbers, transaction IDs, percentage values, dates in data tables.

**Type scale:**
- Display: 52px / 700 / 1.05 — balance display, hero financial figures
- H1: 36px / 700 / 1.15
- H2: 26px / 600 / 1.25
- H3: 20px / 600 / 1.35
- H4: 16px / 600 / 1.4
- Body LG: 18px / 400 / 1.7 — lead paragraphs, key descriptions
- Body: 15px / 400 / 1.65 — default body
- Body SM: 13px / 400 / 1.55 — captions, metadata, table content
- Label: 11px / 600 / 1.4 — uppercase, letter-spacing 0.06em
- Code: 14px / 400 — mono font

**Typography rules:**
- DM Serif Display always sentence case — never all-caps headings
- All currency values, percentages, and financial data in JetBrains Mono — no exceptions
- Body line-height 1.65 minimum — users pause to read and consider financial information

---

## Spacing & Layout

Base unit: 8px — generous enough to breathe, tight enough to feel organized
Scale: 8, 16, 24, 32, 40, 48, 64, 80, 96
Max content width: 1120px
Grid: 12-column, 24px gutter
Density: Default — financial data needs breathing room; users pause to understand, not scan and leave

---

## Border Radius

sm: 6px — input fields, small badges, transaction rows
md: 12px — cards, buttons, chart containers
lg: 20px — modals, account panels, feature cards
full: 9999px — balance pills, category chips (used intentionally — signals this is a "soft" product)

**Radius personality:** Gently rounded — friendly and modern without feeling like a toy. This is approachable finance, not a game.

---

## Shadows & Elevation

sm: 0 1px 3px rgba(28, 28, 26, 0.06), 0 1px 2px rgba(28, 28, 26, 0.04) — subtle card lift
md: 0 4px 12px rgba(28, 28, 26, 0.08), 0 2px 4px rgba(28, 28, 26, 0.04) — dropdowns, standard cards
lg: 0 10px 24px rgba(28, 28, 26, 0.10), 0 4px 8px rgba(28, 28, 26, 0.06) — modals, side panels
xl: 0 20px 48px rgba(28, 28, 26, 0.12), 0 8px 16px rgba(28, 28, 26, 0.08) — overlays, max elevation

**Shadow personality:** Warm-tinted shadows using the near-black text color rather than pure black — maintains the warm palette character even in depth.
**Shadow rules:**
- No shadows on buttons — flat signals confidence
- Dark mode uses Surface Raised (elevation through lightness) rather than shadows

---

## Motion & Animation

**Personality:** Smooth and reassuring — motion should feel like water, never a jolt; users are often checking anxiety-inducing information and should feel calm.

**Durations:**
- Instant: 80ms — toggle states, checkbox
- Fast: 180ms — hover states, small UI changes
- Base: 300ms — content transitions, reveals
- Slow: 450ms — balance updates, chart animations (numbers feel more meaningful when they count up)

**Easing:**
- Enter: cubic-bezier(0.0, 0.0, 0.2, 1.0) — decelerate into view
- Exit: cubic-bezier(0.4, 0.0, 1.0, 1.0) — accelerate out
- Move: cubic-bezier(0.4, 0.0, 0.2, 1.0) — smooth repositioning

**Named transitions:**
- transition-hover: 180ms cubic-bezier(0.0, 0.0, 0.2, 1.0)
- transition-enter: 300ms cubic-bezier(0.0, 0.0, 0.2, 1.0)
- transition-exit: 180ms cubic-bezier(0.4, 0.0, 1.0, 1.0)
- transition-layout: 300ms cubic-bezier(0.4, 0.0, 0.2, 1.0)

**Never:** Celebration animations on spending. Bounce/elastic. Flash. Anything alarming when a number changes. Skeleton shimmer faster than 1.5s loop.

**prefers-reduced-motion:** All transitions collapse to instant (0ms), number count-up animations disabled, balance reveals immediate.

---

## Components

**Buttons:**
- Primary: #2D6A4F bg, #F8F6F2 text, 12px radius, no shadow, 44px min height, hover: darken 8%
- Secondary: transparent bg, #2D6A4F border 1.5px, #2D6A4F text, hover: Linen background
- Ghost: transparent, #DDD9D1 border 1px, Text Primary, hover: Surface background
- Destructive: #9B3B2E bg, white text, same radius
- Disabled: 40% opacity, cursor: not-allowed
- Rules: No gradients. No drop shadows on buttons. Flat signals confidence.

**Cards:**
- Default: Linen bg, Border 1px, 12px radius, shadow-sm, 24px padding
- Interactive hover: shadow-md, border shifts to #C8C4BC — no translate or lift
- Financial figure cards: Display-size mono numbers, Label above, Accent gold for positive deltas

**Inputs:**
- Surface bg, Border 1.5px, 6px radius, Text Primary, 14px padding
- Focus: Primary border 2px, no glow ring — clean not consumer
- Error: Brick border + small Brick label below
- Placeholder: Text Disabled color

**Navigation:**
- Left sidebar on desktop, bottom tab bar on mobile
- Active: Primary left border 3px + Primary text
- Inactive: Text Secondary
- No top nav on mobile — full bottom tab pattern

**Badges & Labels:**
- Status: tinted background (15% opacity) + matching text color
- Category pills: Surface Raised bg, Border, full radius

**Icons:**
- Set: Lucide Icons
- Style: 1.5px stroke, outline only
- Size: 16px inline, 20px standalone, 24px in feature contexts
- Color: Text Secondary for utility, Primary for active states

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
  --color-surface-raised: #E8E3DC;
  --color-border: #DDD9D1;
  --color-text-primary: #1C1C1A;
  --color-text-secondary: #6B6760;
  --color-text-disabled: #A8A49F;
  --color-success: #40916C;
  --color-warning: #C47C1B;
  --color-error: #9B3B2E;
  --color-info: #3A72A8;

  --font-heading: 'DM Serif Display', Georgia, serif;
  --font-body: 'DM Sans', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;

  --text-display: 52px;
  --text-h1: 36px;
  --text-h2: 26px;
  --text-h3: 20px;
  --text-h4: 16px;
  --text-body-lg: 18px;
  --text-body: 15px;
  --text-body-sm: 13px;
  --text-label: 11px;
  --text-code: 14px;

  --space-1: 8px; --space-2: 16px; --space-3: 24px; --space-4: 32px;
  --space-5: 40px; --space-6: 48px; --space-8: 64px; --space-10: 80px; --space-12: 96px;

  --radius-sm: 6px; --radius-md: 12px; --radius-lg: 20px; --radius-full: 9999px;

  --shadow-sm: 0 1px 3px rgba(28,28,26,.06), 0 1px 2px rgba(28,28,26,.04);
  --shadow-md: 0 4px 12px rgba(28,28,26,.08), 0 2px 4px rgba(28,28,26,.04);
  --shadow-lg: 0 10px 24px rgba(28,28,26,.10), 0 4px 8px rgba(28,28,26,.06);
  --shadow-xl: 0 20px 48px rgba(28,28,26,.12), 0 8px 16px rgba(28,28,26,.08);

  --duration-instant: 80ms; --duration-fast: 180ms; --duration-base: 300ms; --duration-slow: 450ms;
  --ease-enter: cubic-bezier(0.0, 0.0, 0.2, 1.0);
  --ease-exit: cubic-bezier(0.4, 0.0, 1.0, 1.0);
  --ease-move: cubic-bezier(0.4, 0.0, 0.2, 1.0);
  --transition-hover: 180ms cubic-bezier(0.0, 0.0, 0.2, 1.0);
  --transition-enter: 300ms cubic-bezier(0.0, 0.0, 0.2, 1.0);
  --transition-layout: 300ms cubic-bezier(0.4, 0.0, 0.2, 1.0);
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-background: #161614;
    --color-surface: #1E1D1A;
    --color-surface-raised: #262420;
    --color-border: #2E2C28;
    --color-text-primary: #E8E4DE;
    --color-text-secondary: #9A9690;
    --color-primary: #3D8C68;
    --color-accent: #C4962A;
  }
}
```

### Tailwind Extension

```js
colors: {
  primary: '#2D6A4F', secondary: '#1B4332', accent: '#D4A853',
  background: '#F8F6F2', surface: '#EFECE6', 'surface-raised': '#E8E3DC',
  border: '#DDD9D1', 'text-primary': '#1C1C1A', 'text-secondary': '#6B6760',
  'text-disabled': '#A8A49F', success: '#40916C', warning: '#C47C1B',
  error: '#9B3B2E', info: '#3A72A8',
},
fontFamily: {
  heading: ['"DM Serif Display"', 'Georgia', 'serif'],
  body: ['"DM Sans"', 'system-ui', 'sans-serif'],
  mono: ['"JetBrains Mono"', '"Courier New"', 'monospace'],
},
borderRadius: { sm: '6px', md: '12px', lg: '20px' },
boxShadow: {
  sm: '0 1px 3px rgba(28,28,26,.06),0 1px 2px rgba(28,28,26,.04)',
  md: '0 4px 12px rgba(28,28,26,.08),0 2px 4px rgba(28,28,26,.04)',
  lg: '0 10px 24px rgba(28,28,26,.10),0 4px 8px rgba(28,28,26,.06)',
},
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. **Colors:** Only defined palette. Never pure `#FFFFFF` — use Background (#F8F6F2). Never pure `#000000` — use Text Primary (#1C1C1A).
2. **Typography:** DM Serif Display for all headings. DM Sans for body. JetBrains Mono for every currency value, percentage, and financial figure — no exceptions.
3. **Spacing:** Only scale values (8px increments). No arbitrary values.
4. **Radius:** Gently rounded throughout. 12px buttons/cards, 6px inputs. Pill shapes only for category chips and balance indicators.
5. **Shadows:** shadow-sm for default cards. shadow-md for interactive states and dropdowns. No shadows on buttons.
6. **Motion:** transition-hover for all interactive states. Nothing jarring when financial numbers change. Accent gold only for positive financial moments.
7. **Dark mode:** Apply dark mode CSS variable overrides when `prefers-color-scheme: dark` or `data-theme="dark"`.
8. **Scope:** This file controls visuals only. Do NOT change copy, content, features, or UX structure.
9. **Archetype check:** Does this feel like a calm, knowledgeable friend helping with money? If it feels like a bank portal or a trading app, simplify and warm it.
