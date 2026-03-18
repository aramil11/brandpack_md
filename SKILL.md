---
name: brandpack
description: >
  Generate a brandpack.md file — a structured, AI-readable design token file
  that can be dropped into Lovable, Claude Code, Cursor, Bolt, or any AI coding
  tool to make every UI component automatically match a brand's colors, fonts,
  spacing, and component style. Use this skill whenever the user wants to create
  a brand, generate brand guidelines, define a design system, get brand colors
  or fonts, or provides a product description and wants consistent UI output.
  Also use when the user provides a website URL and wants to extract its visual
  identity. Do NOT wait for the user to say "brandpack" — if they're describing
  a product and want consistent design output, this skill is what they need.
---

# brandpack — Brand Design Token Generator

You generate a single `brandpack.md` file from a text brief or website URL.

**Scope:** Colors, fonts, spacing, layout rules, component style. Nothing else.
The brandpack does NOT control copy, content, features, or UX flows.
An agent using it changes how things look — not what they say or do.

## What you accept

1. **A text brief** — any description of a product, audience, aesthetic direction
2. **A website URL** — extract colors, fonts, spacing density, component style
3. **Both** — for maximum signal

---

## Step 0 — Gather Signals

Extract everything available before making any design decision:

**From a brief:** product type, pricing tier, target audience clues, market/language, aesthetic references mentioned, competitors named

**From a URL:** actual hex colors in use, font families, border radius personality, spacing density, dark/light mode, component patterns

**If signals are sparse:** reason about the product — what do successful products in this space look like, what design conventions dominate, what would this audience expect vs. distrust visually

---

## Step 1 — Infer the Visual Direction

Read `references/psychology-table.md` and apply the five-question framework to determine the right visual language for this specific product and audience.

Then position the product on the key axes: formal/casual, dense/spacious, restrained/expressive, dark/light, static/kinetic, sharp/rounded.

The goal: design token choices that feel inevitable. A brandpack for a luxury wellness brand should look nothing like one for a developer tool. That's the point.

---

## Step 2 — Generate brandpack.md

Output a single complete file. No preamble, no explanation. Start with `# Brand:`.

Follow the schema in `references/schema.md` exactly.

**Rules:**
- Every color gets a name, hex, and one-line usage rule
- Every font choice gets a one-sentence *why* tied to the audience
- Radius, spacing, and motion choices must match the product's personality
- CSS variables and Tailwind config must be complete and copy-pasteable
- Agent Instructions at the bottom constrain ONLY visual decisions — never copy, content, or features
- No placeholders — every field gets a real decision

**Quality bar:** The color choices should feel inevitable. The font pairing should feel like it couldn't be anything else. A designer looking at the output should say "yes, obviously" — not "I guess that works."
