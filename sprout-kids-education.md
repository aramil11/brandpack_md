# Brand: Sprout
> A reading and phonics app for children aged 4–8 — joyful, encouraging, designed to be used by small hands on a tablet screen.

---

## Visual Identity

**Aesthetic:** Playful warmth
**Mode:** Light
**References:** Duolingo (approachable, rewarding, progress-forward), Headspace's illustration style (friendly, rounded, character-driven), Barefoot Books (warm, hand-crafted, inclusive)
**Never look like:** A school textbook (clinical, grey, intimidating). An adult productivity app (dense, cold, text-heavy).

---

## Colors

Primary: #F95F62 — warm coral-red, main CTAs, key actions, primary interaction
Secondary: #3BBFA1 — teal, supporting actions, correct answer states
Accent: #F7B731 — warm yellow, rewards, stars, celebratory moments
Background: #FFFDF7 — very warm white, never cold
Surface: #FFF5E6 — cards, lesson panels
Border: #EDDDCC — dividers, panel edges
Text Primary: #2C2318 — headings, body — warm near-black
Text Secondary: #8A7A65 — captions, instructions
Success: #3BBFA1 — correct, completed, great job
Warning: #F7B731 — hint needed, try again
Error: #F95F62 — incorrect — same as primary so it never feels punishing

Rules:
- Error uses the same coral as Primary — incorrect answers should never feel alarming or shaming
- Accent yellow reserved for stars, rewards, and celebration only — not general UI
- Colors are saturated but warm — never cold primaries (no pure blue, pure green, or pure red)

---

## Typography

Heading: Nunito — https://fonts.google.com/specimen/Nunito
Why: Rounded terminals and friendly weight signal approachability; widely used in children's educational contexts because the letterforms are clear and non-intimidating for early readers.

Body: Nunito — https://fonts.google.com/specimen/Nunito
Why: Single family keeps the visual environment calm; variety comes from weight and size, not font switching, which reduces cognitive load for young learners.

Mono: (not used in this product)
For: N/A — no technical data in a children's reading app

Scale:
- Display: 52px / 800 — reward screens, level titles
- H1: 38px / 700
- H2: 28px / 700
- H3: 22px / 600
- Body: 18px / 500 / line-height 1.7 — larger than adult defaults; children need more space
- Body SM: 15px / 400
- Label: 13px / 700 — sentence case, not uppercase — uppercase is harder for early readers
- Data: N/A

Rules:
- All text sentence case — uppercase is harder to read for children learning letter shapes
- Body text minimum 18px — small text excludes young readers and strains developing eyes
- Never more than 8 words per line in lesson content — keep reading manageable

---

## Spacing & Layout

Base unit: 8px
Scale: 8, 16, 24, 32, 48, 64, 80
Max width: 800px (tablet-first)
Grid: single column, generous padding
Density: Very spacious — children need large tap targets and uncluttered screens; cognitive load must be minimal

---

## Border Radius

sm: 12px — small badges, tags
md: 20px — buttons, cards, answer options
lg: 32px — lesson panels, modals
full: 9999px — avatars, progress dots, reward badges

Personality: Very rounded throughout — soft shapes signal safety and playfulness; nothing sharp or angular in a children's product.

---

## Components

Buttons:
- Primary: #F95F62 background, #FFFDF7 text, 20px radius, subtle drop shadow (0 4px 0 #C94548), hover: translate up 2px
- Secondary: #3BBFA1 background, #FFFDF7 text, 20px radius, shadow (0 4px 0 #2A9980)
- Answer option: Surface background, Border 2px, 20px radius, 24px padding — selected: Primary border 3px + light primary tint background
- Rules: Minimum 56px height — designed for small fingers. Pressed state: shadow collapses (translateY +4px). This is tactile by design.

Cards:
- Surface background (#FFF5E6), Border 2px solid Border color, 24px radius, 24px padding
- Correct state: Success border (#3BBFA1) + Success tint background
- No hover states — this is a touch-first product

Inputs:
- Surface background, Border 2px, 16px radius, Text Primary, 18px font
- Focus: Primary border 3px — children need clear visible focus
- Never placeholder text in learning inputs — use illustrated hints instead

Navigation:
- Bottom tab bar, large icons + labels, 64px height
- Active: Primary color icon + Primary color label
- Inactive: Text Secondary

Icons:
- Phosphor Icons, Fill weight (solid, not outline — easier to perceive for young children)
- 28px minimum size everywhere
- Colored per context — success teal, reward yellow, action coral

---

## Motion

Personality: Bouncy and rewarding — motion celebrates progress and makes learning feel like play; but never distracting during active learning moments.
Default: 250ms ease-out for transitions / 400ms spring for rewards
Hover/press: Buttons compress on press (scale 0.95, 80ms). Release: scale returns with spring.
Reward moments: Stars burst, characters jump, confetti — Accent yellow dominant, 600ms max, never loops.
Never: Motion during active reading or phonics exercises. Anything that moves when the child is trying to focus on text.

---

## Code

### CSS Variables

```css
:root {
  --color-primary: #F95F62;
  --color-secondary: #3BBFA1;
  --color-accent: #F7B731;
  --color-background: #FFFDF7;
  --color-surface: #FFF5E6;
  --color-border: #EDDDCC;
  --color-text-primary: #2C2318;
  --color-text-secondary: #8A7A65;
  --color-success: #3BBFA1;
  --color-warning: #F7B731;
  --color-error: #F95F62;

  --font-heading: 'Nunito', system-ui, sans-serif;
  --font-body: 'Nunito', system-ui, sans-serif;
  --font-mono: 'Nunito', system-ui, sans-serif;

  --space-1: 8px; --space-2: 16px; --space-3: 24px; --space-4: 32px;
  --space-6: 48px; --space-8: 64px;

  --radius-sm: 12px; --radius-md: 20px; --radius-lg: 32px; --radius-full: 9999px;

  --transition-fast: 250ms ease-out;
  --transition-base: 400ms cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

### Tailwind Extension

```js
colors: {
  primary: '#F95F62', secondary: '#3BBFA1', accent: '#F7B731',
  background: '#FFFDF7', surface: '#FFF5E6', border: '#EDDDCC',
  'text-primary': '#2C2318', 'text-secondary': '#8A7A65',
  success: '#3BBFA1', warning: '#F7B731', error: '#F95F62',
},
fontFamily: {
  heading: ['Nunito', 'system-ui', 'sans-serif'],
  body: ['Nunito', 'system-ui', 'sans-serif'],
  mono: ['Nunito', 'system-ui', 'sans-serif'],
},
borderRadius: { sm: '12px', md: '20px', lg: '32px' },
```

### Font Import

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

---

## Agent Instructions

When this brandpack.md is in your context:

1. Use only the colors defined above. Warm palette only — never introduce cold blues, greys, or stark whites.
2. Nunito for everything — heading, body, labels. No font switching.
3. All text sentence case. Never uppercase. Minimum 18px body text.
4. Radius is generous throughout — 20px+ for interactive elements, 32px for panels. Nothing sharp.
5. Tap targets minimum 56px height. This is a touch-first, child-first product.
6. Reward motion (stars, confetti) uses Accent yellow and spring easing. Motion during active learning: none.
7. Error states use Primary coral — incorrect is never alarming or shaming.
8. Do NOT change copy, content, features, or UX structure. This file controls visuals only.
9. When in doubt: would a 5-year-old find this inviting and easy to tap? If it looks like an adult app, make it softer, bigger, and warmer.
