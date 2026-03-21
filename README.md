# brandpack.md

**Turn a one-line brief — or an existing codebase — into a complete brand design system.**  
Drop the output into Lovable, Claude Code, Cursor, Bolt, or any AI coding tool  
and every component it builds will automatically match your brand.

---

## The problem

Every AI-built app looks the same.

Inter font. #3B82F6 blue. 8px border radius. Generic SaaS shadows.

Not because the tools are bad. Because they have no brand context.  
`brandpack.md` fixes this. One file. Works anywhere.

---

## What it generates

A single `brandpack.md` with your complete visual design system:

- **Colors** — full palette with evocative names, usage rules, and color psychology
- **Dark mode overrides** — proper token overrides (not just CSS inversion)
- **Typography** — distinctive font pairing with reasoning, full type scale
- **Spacing & layout** — base unit, scale, max width, grid, density reasoning
- **Shadows & elevation** — named shadow tokens that match the brand personality
- **Motion & animation** — named transitions, durations, easing, and explicit ban list
- **Component specs** — buttons, cards, inputs, nav, badges, icons — fully specified
- **Ready-to-use code** — CSS variables + Tailwind config + font import tag
- **Agent Instructions** — baked-in rules that tell any AI exactly how to apply it

---

## Three ways to generate

### From a brief
```
Generate a brandpack for: a personal finance app for people who want to understand
their money, not just track it — calm, intelligent, never preachy.
```

### From a website URL
```
Generate a brandpack from: https://yourcompetitor.com
```
Extracts actual computed colors, fonts, spacing, and component patterns from the rendered UI.

### From a GitHub repo
```
Generate a brandpack from: https://github.com/you/your-project
```
Reads `tailwind.config.js`, CSS variables, and component files. Extracts what's already there,
resolves inconsistencies, fills gaps. Every token is annotated:
`[extracted: tailwind.config]` or `[inferred: no background token found]`

---

## How to use the output

### In Lovable
Add `brandpack.md` to your project's Knowledge section, or paste it into your first prompt:
```
Use the brandpack below for all design decisions. Do not deviate from it.
[paste brandpack.md]
Now build: [your app description]
```

### In Claude Code / Cursor / Windsurf
Add `brandpack.md` to your project root:
```
Use @brandpack.md for all styling decisions.
```

### In any other AI tool
Paste the contents into the system prompt. The **Agent Instructions** section at the bottom
is self-executing — it tells any AI exactly what to follow and what to avoid.

### Via CDN *(coming soon)*
```
https://brandpack.md/[your-brand]
```

---

## Optional: browser verification

If you have the [browse skill](https://github.com/garrytan/gstack) installed, the skill can
generate a demo HTML page using your brandpack tokens, open it in a headless browser,
take responsive screenshots at mobile/tablet/desktop, and check for visual issues — before
you drop it into your actual project.

---

## Examples

| | Product | Aesthetic | Mode |
|---|---|---|---|
| [→](examples/vault-personal-finance.md) | Vault — personal finance | Warm financial clarity | Light + Dark |
| [→](examples/forge-developer-tool.md) | Forge — CI/CD platform | Dark precision | Dark only |

Same skill. Different products. Completely different outputs.

---

## Install

```bash
git clone https://github.com/[handle]/brandpack.md
```

Add the folder to your Claude skills directory. All files must be present:

```
brandpack.md/
├── SKILL.md                          ← skill entrypoint
├── references/
│   ├── schema.md                     ← output format
│   ├── psychology-table.md           ← visual reasoning framework
│   └── verification.md              ← browser-based visual check (optional)
└── examples/
    └── ...
```

---

## What brandpack.md does NOT do

- Change your copy or content
- Decide your features or UX flows
- Control navigation structure or information architecture

**It controls visuals only.** How things look — not what they say or do.

---

## Contributing

- **Brief that produces weak output?** Open an issue with the brief.
- **Great brandpack you want to share?** Add it to `examples/` as a PR.
- **Improvement to the reasoning framework?** `references/psychology-table.md`.

---

## License

MIT
