---
name: brandpack
description: >
  Generate a brandpack.md file — a complete, AI-readable brand design system that
  can be dropped into Lovable, Claude Code, Cursor, Bolt, or any AI coding tool to
  make every UI component automatically match a brand's colors, fonts, spacing, shadows,
  motion, and component style. Use this skill whenever the user wants to create a brand,
  generate brand guidelines, define a design system, get brand colors or fonts, extract
  a visual identity from a website or codebase, or provides a product description and
  wants consistent UI output. Do NOT wait for the user to say "brandpack" — if they
  are describing a product and want consistent design output, this skill is what they need.
  Also triggers on: "design system", "brand guidelines", "color palette for my app",
  "make it look like X", "extract the brand from this URL", "standardize my UI".
---

# brandpack — Brand Design System Generator

You generate a single `brandpack.md` file from a text brief, website URL, or GitHub repo.

**Scope:** Colors, typography, spacing, shadows, motion, layout, component style. Nothing else.
The brandpack does NOT control copy, content, features, or UX flows.
An agent using it changes how things look — not what they say or do.

---

## What you accept

1. **A text brief** — any description of a product, audience, or aesthetic direction
2. **A website URL** — extract the visual identity from the rendered product
3. **A GitHub repo URL** — extract from source files (Tailwind config, CSS variables, components)
4. **Any combination** — more inputs = more accurate output

---

## Step 0 — Gather Every Signal

Before making any design decision, extract everything available.

**From a brief:** product type, business model (B2B/B2C/SaaS/marketplace), pricing tier,
target audience clues (age, profession, market, culture), aesthetic references mentioned,
competitors named, problem being solved (functional vs emotional), stage (MVP vs scaling).

**From a URL:** fetch the page, then extract:
- Actual hex colors in use (backgrounds, CTAs, text, borders)
- Font families (from Google Fonts links, CSS font-family declarations)
- Border radius personality across components
- Spacing density (compact vs spacious)
- Shadow usage and depth
- Dark or light mode
- Animation personality (fast/snappy vs slow/deliberate)
- Overall aesthetic archetype (what does this feel like?)

**From a repo:** read `tailwind.config.js/ts`, `globals.css`, `variables.css`, key component
files. Extract existing tokens. Note inconsistencies — same element styled differently across
files. These get resolved and documented in the brandpack.

**If signals are sparse:** reason about the product category and audience. Ask: what do
the top 3–5 products in this space look like? What design conventions dominate? What would
this audience trust vs. distrust on first sight?

---

## Step 1 — Audience & Visual Direction

Read `references/psychology-table.md` and work through the five-question framework.
Then position the product on the key axes:

- **Formal ←→ Casual** (font choice, button style, density)
- **Dense ←→ Spacious** (expert users vs high-consideration decisions)
- **Restrained ←→ Expressive** (authority vs personality)
- **Dark ←→ Light** (technical/premium vs transparent/professional)
- **Sharp ←→ Rounded** (institutional vs consumer)
- **Static ←→ Kinetic** (high-stakes vs exploratory)

The goal: every token choice feels inevitable for this specific product and audience.
A compliance platform and a children's education app should produce completely different brandpacks.

---

## Step 2 — Generate brandpack.md

Output a single complete file. No preamble, no explanation. Start with `# Brand:`.

Follow the schema in `references/schema.md` exactly. Every section required. No placeholders.

**Non-negotiable quality standards:**

- **Colors must be genuinely beautiful together.** Before finalizing, mentally render a hero
  section: heading in the chosen font, body text, a primary CTA button, on the chosen background.
  Does it look like a well-designed product site, or a Tailwind starter template? If the latter,
  change the colors. Never use `#3B82F6` (generic Tailwind blue), `#6366F1` (generic purple),
  `#10B981` (generic green), or pure white `#FFFFFF` as background — these scream "AI default."

- **Font pairings must have visual tension.** A distinctive display or heading font paired with
  a clean, highly legible body font. Never default to Inter + Inter or Inter + Roboto.
  Avoid overused pairings: Playfair + Lato, Montserrat + Open Sans, Space Grotesk + anything.

- **Every decision is traceable.** Not "blue = trust" — but WHY this specific shade, for this
  audience, in this market, at this price point. The reasoning should be in the font `Why:` and
  color psychology notes.

- **Specificity beats vagueness always.**
  Bad: `warm and approachable`
  Good: `#F2E4D0 — evokes handmade paper, signals craft without being rustic, never clinical`

- **The AI slop check.** Before outputting, scan for these patterns and eliminate them:
  - Purple/violet gradient backgrounds or blue-to-purple gradients
  - Icons-in-colored-circles as decorative elements
  - Uniform large border-radius on every single element
  - Bright saturated primary colors with no secondary palette
  - Generic neutral grays with no warmth or coolness character
  - Inter as heading font with no display face

---

## Step 3 — Optional: Browser Verification

If the browse tool is available AND the user wants to verify the output looks good,
read `references/verification.md` and follow the visual verification workflow.

This generates a minimal HTML demo page using all the brandpack tokens, opens it
in a browser, takes responsive screenshots, and checks for visual issues.
