# brandpack.md

**Turn a one-line brief — or an existing codebase — into a complete brand design system.**  
Drop the output into Lovable, Claude Code, Cursor, Bolt, or any AI coding tool  
and every component it builds will automatically match your brand.

---

## The problem

Every AI-built app looks the same.

Inter font. #3B82F6 blue. 8px border radius. Generic SaaS shadows.

Not because the tools are bad. Because they have no brand context.
**brandpack.md** fixes this. One file. Works anywhere.

---

## Three ways to generate a brandpack

### 1. From a brief
Describe your product. The skill reasons about your audience and generates a complete design system from scratch.

```
Brief: "A personal finance app for people who want to understand 
their money, not just track it — calm, intelligent, never preachy."
```

### 2. From a website URL
Point it at any live product. The skill extracts colors, fonts, spacing, and component patterns from the rendered UI.

```
URL: https://yourproduct.com
```

### 3. From a GitHub repo ← new
Point it at your codebase. The skill reads your actual source files — Tailwind config, CSS variables, component files — extracts what's already there, resolves inconsistencies, fills gaps, and produces a brandpack that becomes the source of truth for all future development.

```
Repo: https://github.com/you/your-project
```

What gets extracted from a repo:
- `tailwind.config.js` — existing color tokens, font families, radius scale
- Global CSS files — CSS custom properties already defined
- Font imports — Google Fonts links, `@font-face` declarations
- Component files — actual button, card, input, nav patterns in use
- Inconsistencies — same element styled differently across files, gets flagged and resolved

The output documents what was **extracted from code** vs. what was **inferred or added** — so you always know exactly where each decision came from.

---

## What the output looks like

```markdown
# Brand: Vault
> A personal finance app — calm, intelligent, warm.

## Colors
Primary: #2D6A4F — [extracted: tailwind.config] — CTAs, active states
Background: #F8F6F2 — [inferred: no bg token found] — warm off-white, never stark

## Typography
Heading: DM Serif Display — warm serif, signals trust without banking coldness
Body: DM Sans — matched family, highly legible for data-dense financial views

## Agent Instructions
1. Use only the colors defined above. Never introduce new colors.
2. DM Serif Display for headings. DM Sans for body.
3. JetBrains Mono for every currency value and financial figure — no exceptions.
4. This file is the source of truth. Existing code that contradicts it should 
   be updated to match, not the other way around.
...
```

---

## How to use it

### In Lovable
Add `brandpack.md` to your project's Knowledge section, or paste it into your first prompt:
```
Use the brandpack below for all design decisions. Do not deviate from it.
[paste brandpack.md]
Now build: [your app]
```

### In Claude Code / Cursor / Windsurf
Add `brandpack.md` to your project root:
```
Use @brandpack.md for all styling decisions.
```

### In any other AI tool
Paste the contents into the system prompt or context window. The **Agent Instructions** section at the bottom is self-executing — it tells any AI exactly what to follow.

### Via CDN *(coming soon)*
Host your brandpack at a stable URL and reference it from anywhere:
```
https://brandpack.md/[your-brand]
```

---

## Examples

Four fictional products showing the full range:

| | Product | Aesthetic | Mode |
|---|---|---|---|
| [→](examples/vault-personal-finance.md) | Vault — personal finance | Warm financial clarity | Light |
| [→](examples/forge-developer-tool.md) | Forge — CI/CD platform | Dark precision | Dark |
| [→](examples/solis-luxury-wellness.md) | Solis — luxury wellness | Quiet luxury | Light |
| [→](examples/sprout-kids-education.md) | Sprout — children's education | Playful warmth | Light |

Same skill. Four completely different outputs.

---

## Install the skill

```bash
git clone https://github.com/[handle]/brandpack.md
```

Add the folder to your Claude skills directory. All three files must be present:

```
brandpack.md/
├── SKILL.md                        ← skill entrypoint
├── references/
│   ├── schema.md                   ← output format
│   └── psychology-table.md         ← visual reasoning framework
└── examples/
    └── ...
```

Then in any Claude conversation:
```
Generate a brandpack for: [brief / URL / repo]
```

---

## What brandpack.md does NOT do

- Change your copy or content
- Decide your features or UX flows
- Rewrite your navigation structure

**It controls visuals only.** Colors, fonts, spacing, radius, motion, components.  
How things look — not what they say or do.

---

## Contributing

- **Brief that produces a weak output?** Open an issue.
- **Great brandpack output?** Add it to `examples/` as a PR.
- **Improvement to the reasoning framework?** `references/psychology-table.md` is the place.

---

## License

MIT
