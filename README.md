# brandpack.md

**Turn a one-line brief into a complete brand design system.**  
Drop the output into Lovable, Claude Code, Cursor, Bolt, or any AI coding tool —  
and every component it builds will automatically match your brand.

---

## The problem

Every AI-built app looks the same.

Inter font. #3B82F6 blue. 8px border radius. Generic SaaS shadows.

Not because the tools are bad. Because they have no brand context.
They're building in a vacuum. `brandpack.md` fixes this.

---

## What it is

A single `.md` file that any AI coding agent can read — containing your complete visual design system:

- **Colors** — every role defined with hex, name, and usage rule
- **Typography** — font pairing with reasoning, full type scale  
- **Spacing & layout** — base unit, scale, max width, density rules
- **Border radius** — tokens with personality reasoning
- **Components** — buttons, cards, inputs, nav, icons
- **Motion** — personality, durations, explicit ban list
- **Ready-to-use code** — CSS variables + Tailwind config + font import tag
- **Agent Instructions** — baked-in rules that tell any AI exactly what to follow

One file. Works anywhere.

---

## How it works

You describe your product. The skill reasons about your audience, infers the right visual direction, and generates a complete brandpack.

```
Brief: "A personal finance app for people who want to understand 
their money, not just track it — calm, intelligent, never preachy."
```

↓

```markdown
# Brand: Vault
> Calm, intelligent, never preachy.

## Colors
Primary: #2D6A4F — CTAs, active states, key actions
Background: #F8F6F2 — warm off-white, never stark white
...

## Typography  
Heading: DM Serif Display — warm serif, signals trustworthiness
Body: DM Sans — matched family, legible at small sizes
...

## Agent Instructions
1. Use only the colors defined above.
2. DM Serif Display for headings. DM Sans for body.
3. JetBrains Mono for every currency value and financial figure.
...
```

The skill doesn't just pick colors — it reasons about why.  
A finance app and a kids' education app produce completely different outputs.  
That's the point.

---

## Usage

### Option A — Paste into Lovable

Add `brandpack.md` to your Lovable project's Knowledge section, or paste directly into your first prompt:

```
Use the brandpack below for all design decisions.
Do not deviate from it.

[paste brandpack.md contents here]

Now build: [your app description]
```

### Option B — Claude Code / Cursor / Windsurf

Add `brandpack.md` to your project root:

```
Use @brandpack.md for all styling decisions.
```

### Option C — Any other AI tool

Paste the contents into the system prompt or context window.  
The **Agent Instructions** section at the bottom is self-executing — it tells any AI exactly what to do.

### Option D — CDN (coming soon)

Host your brandpack at a stable URL and reference it from anywhere:

```
https://brandpack.md/[your-brand]
```

---

## Generate your brandpack

If you have the Claude skill installed:

```
Generate a brandpack for: [your brief]
```

Or extract from an existing website:

```
Generate a brandpack from: https://yourcompetitor.com
```

Or both — brief + URL gives the most accurate output.

---

## Examples

Four fictional products showing the full range of what the skill produces:

| Product | Aesthetic | Mode | Key choices |
|---|---|---|---|
| [Vault](examples/vault-personal-finance.md) — personal finance | Warm financial clarity | Light | DM Serif + DM Sans, muted green, warm off-white |
| [Forge](examples/forge-developer-tool.md) — CI/CD platform | Dark precision | Dark | Inter mono-family, near-black base, status color system |
| [Solis](examples/solis-luxury-wellness.md) — luxury wellness | Quiet luxury | Light | Cormorant Garamond, near-black primary, near-square radius |
| [Sprout](examples/sprout-kids-education.md) — children's education | Playful warmth | Light | Nunito everywhere, coral + teal, 20px radius, spring motion |

Same skill. Four completely different outputs.  
That's the point.

---

## Repo structure

```
brandpack/
├── SKILL.md                        ← Install this as a Claude skill
├── references/
│   ├── schema.md                   ← Output format (read by the skill)
│   └── psychology-table.md         ← Visual reasoning framework
└── examples/
    ├── vault-personal-finance.md
    ├── forge-developer-tool.md
    ├── solis-luxury-wellness.md
    └── sprout-kids-education.md
```

---

## Install the skill

```bash
git clone https://github.com/[handle]/brandpack
```

Then add the `brandpack/` folder to your Claude skills directory.

The skill references `references/schema.md` and `references/psychology-table.md` automatically — all three files must be present.

---

## What brandpack.md does NOT do

- Change your copy or content
- Decide your features or UX flows  
- Control navigation structure
- Write your microcopy

**It controls visuals only.** How things look, not what they say or do.  
This is a design token file. A very good one.

---

## The before/after

> *(Demo video coming — PRs with before/after screenshots welcome)*

---

## Contributing

The skill gets better with more real-world edge cases.

- **Found a brief that produces a weak output?** Open an issue with the brief and describe what was wrong.
- **Built a great brandpack manually?** Add it to `examples/` as a PR.
- **Improved the reasoning framework?** The psychology table in `references/` is the right place.

---

## License

MIT — use it, fork it, build on it.
