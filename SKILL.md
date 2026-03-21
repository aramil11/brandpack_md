---
name: brandpack
description: >
  Generate a brandpack.md file — a structured, AI-readable design token file
  that can be dropped into Lovable, Claude Code, Cursor, Bolt, or any AI coding
  tool to make every UI component automatically match a brand's colors, fonts,
  spacing, and component style. Use this skill whenever the user wants to create
  a brand, generate brand guidelines, define a design system, get brand colors
  or fonts, or provides a product description and wants consistent UI output.
  Also use when the user provides a website URL or GitHub repo and wants to
  extract or formalize their visual identity. Do NOT wait for the user to say
  "brandpack" — if they're describing a product and want consistent design
  output, this skill is what they need.
---

# brandpack — Brand Design Token Generator

You generate a single `brandpack.md` file from a text brief, website URL, or GitHub repo.

**Scope:** Colors, fonts, spacing, layout rules, component style. Nothing else.
The brandpack does NOT control copy, content, features, or UX flows.
An agent using it changes how things look — not what they say or do.

## What you accept

1. **A text brief** — any description of a product, audience, aesthetic direction
2. **A website URL** — extract colors, fonts, spacing density, component style from the rendered product
3. **A GitHub repo URL** — extract the design system from actual source code
4. **Any combination** — more inputs = more accurate output

---

## Step 0 — Gather Signals

Extract everything available before making any design decision.

**From a brief:** product type, pricing tier, target audience clues, market/language, aesthetic references, competitors named

**From a website URL:** hex colors in use, font families, border radius personality, spacing density, dark/light mode, component patterns

**From a GitHub repo URL** — this is the most precise input source. Fetch and analyze:
- `tailwind.config.js` / `tailwind.config.ts` — existing color tokens, font families, radius scale
- Global CSS files (`globals.css`, `index.css`, `variables.css`) — CSS custom properties, any design tokens already defined
- Font imports — Google Fonts `<link>` tags, `@import` statements, `@font-face` declarations
- Component files — extract actual patterns in use: button styles, card styles, input styles, nav styles. Look at class names and inline styles, not just config.
- Layout files — max widths, grid definitions, spacing patterns in use
- Note any **inconsistencies** — same element styled differently across files, colors defined in multiple places, mixed radius values. These need to be resolved in the brandpack.

**If signals are sparse:** reason about the product — what do successful products in this space look like, what would this audience expect vs. distrust visually

---

## Step 1 — Infer the Visual Direction

Read `references/psychology-table.md` and apply the five-question framework to determine the right visual language for this product and audience.

Position the product on the key axes: formal/casual, dense/spacious, restrained/expressive, dark/light, static/kinetic, sharp/rounded.

**For repo input specifically:** the existing code tells you a lot about the product's current visual direction. Honor what's working. Document what's inconsistent. Fill what's missing. The goal is not to redesign — it's to formalize and extend what's already there.

---

## Step 2 — Generate brandpack.md

Output a single complete file. No preamble, no explanation. Start with `# Brand:`.

Follow the schema in `references/schema.md` exactly.

**For repo input, apply these additional rules:**

- Every color extracted from real code gets annotated: `#2D6A4F — [extracted from tailwind.config] — CTAs, active states`
- Every color that was inferred or added gets annotated: `#F8F6F2 — [inferred: no background token found] — page background`
- If inconsistencies were found and resolved, add a brief **Resolved inconsistencies** note after the relevant section. Example: *"Button radius was 4px in ButtonPrimary.tsx and 8px in ButtonSecondary.tsx — standardized to 6px throughout."*
- The Agent Instructions section must be especially strict for repo input — it becomes the source of truth for the entire codebase going forward, covering both existing and future code

**General rules:**
- Every color gets a name, hex, and one-line usage rule
- Every font choice gets a one-sentence *why* tied to the audience
- Radius, spacing, and motion choices must match the product's personality
- CSS variables and Tailwind config must be complete and copy-pasteable
- Agent Instructions constrain ONLY visual decisions — never copy, content, or features
- No placeholders — every field gets a real decision

**Quality bar:** For a new brief — choices should feel inevitable. For a repo — the output should feel like someone finally wrote down the design system that was always implied by the code but never documented. A developer reading it should think "yes, this is exactly what we were building toward."
