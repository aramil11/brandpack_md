# brandpack Verification — Browser-Based Visual Check

After generating a brandpack.md, optionally verify it looks genuinely good by
generating a demo page and opening it in a browser.

Only run this step if:
- The browse tool is available
- The user asked to verify, OR you're not confident the output is beautiful

---

## Step 1 — Generate the demo page

Create a minimal HTML file at `/tmp/brandpack-demo.html` that exercises all the tokens:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>brandpack demo</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<!-- INSERT FONT IMPORT FROM BRANDPACK -->
<style>
/* INSERT ALL CSS VARIABLES FROM BRANDPACK */

* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  background: var(--color-background);
  color: var(--color-text-primary);
  font-family: var(--font-body);
  font-size: var(--text-body);
  line-height: 1.6;
}

.demo-container { max-width: 960px; margin: 0 auto; padding: var(--space-8); }
.section { margin-bottom: var(--space-12); }

/* Typography */
.demo-display { font-family: var(--font-heading); font-size: var(--text-display); line-height: 1.1; font-weight: 700; margin-bottom: var(--space-4); }
.demo-h1 { font-family: var(--font-heading); font-size: var(--text-h1); font-weight: 700; margin-bottom: var(--space-3); }
.demo-h2 { font-family: var(--font-heading); font-size: var(--text-h2); font-weight: 600; margin-bottom: var(--space-3); }
.demo-h3 { font-family: var(--font-heading); font-size: var(--text-h3); font-weight: 600; margin-bottom: var(--space-2); }
.demo-body { font-size: var(--text-body); margin-bottom: var(--space-3); color: var(--color-text-primary); }
.demo-secondary { font-size: var(--text-body-sm); color: var(--color-text-secondary); }
.demo-label { font-size: var(--text-label); font-weight: 600; text-transform: uppercase; letter-spacing: 0.06em; color: var(--color-text-secondary); }
.demo-code { font-family: var(--font-mono); font-size: var(--text-code); background: var(--color-surface); padding: 2px 6px; border-radius: var(--radius-sm); }

/* Buttons */
.btn-row { display: flex; gap: var(--space-3); flex-wrap: wrap; align-items: center; margin-bottom: var(--space-4); }
.btn { display: inline-flex; align-items: center; justify-content: center; padding: 10px 20px; border-radius: var(--radius-md); font-family: var(--font-body); font-size: var(--text-body); font-weight: 500; cursor: pointer; transition: var(--transition-hover); border: none; }
.btn-primary { background: var(--color-primary); color: var(--color-background); }
.btn-secondary { background: transparent; color: var(--color-primary); border: 1.5px solid var(--color-primary); }
.btn-ghost { background: transparent; color: var(--color-text-primary); border: 1.5px solid var(--color-border); }
.btn-destructive { background: var(--color-error); color: white; }
.btn-disabled { opacity: 0.4; cursor: not-allowed; background: var(--color-border); color: var(--color-text-secondary); }

/* Cards */
.card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: var(--space-4); margin-bottom: var(--space-4); }
.card { background: var(--color-surface); border: 1px solid var(--color-border); border-radius: var(--radius-md); padding: var(--space-4); box-shadow: var(--shadow-sm); }
.card-raised { background: var(--color-surface-raised); border: 1px solid var(--color-border); border-radius: var(--radius-md); padding: var(--space-4); box-shadow: var(--shadow-md); }

/* Inputs */
.input-group { display: flex; flex-direction: column; gap: var(--space-2); margin-bottom: var(--space-4); max-width: 400px; }
.demo-input { background: var(--color-surface); border: 1.5px solid var(--color-border); border-radius: var(--radius-sm); padding: 10px 14px; font-family: var(--font-body); font-size: var(--text-body); color: var(--color-text-primary); }
.demo-input:focus { outline: none; border-color: var(--color-primary); }

/* Colors */
.color-grid { display: flex; flex-wrap: wrap; gap: var(--space-2); margin-bottom: var(--space-4); }
.color-chip { width: 64px; height: 64px; border-radius: var(--radius-sm); border: 1px solid var(--color-border); }

/* Status */
.status-row { display: flex; gap: var(--space-3); flex-wrap: wrap; margin-bottom: var(--space-4); }
.badge { display: inline-flex; align-items: center; padding: 4px 12px; border-radius: var(--radius-sm); font-size: var(--text-label); font-weight: 600; }
.badge-success { background: color-mix(in srgb, var(--color-success) 15%, transparent); color: var(--color-success); }
.badge-warning { background: color-mix(in srgb, var(--color-warning) 15%, transparent); color: var(--color-warning); }
.badge-error { background: color-mix(in srgb, var(--color-error) 15%, transparent); color: var(--color-error); }
.badge-info { background: color-mix(in srgb, var(--color-info) 15%, transparent); color: var(--color-info); }

/* Hero preview */
.demo-hero { background: var(--color-surface); border-radius: var(--radius-lg); padding: var(--space-12) var(--space-8); text-align: center; margin-bottom: var(--space-12); border: 1px solid var(--color-border); }
.section-label { font-size: var(--text-label); font-weight: 600; text-transform: uppercase; letter-spacing: 0.08em; color: var(--color-text-secondary); margin-bottom: var(--space-4); padding-bottom: var(--space-2); border-bottom: 1px solid var(--color-border); }
</style>
</head>
<body>
<div class="demo-container">

  <div class="demo-hero">
    <p class="demo-label" style="margin-bottom: var(--space-3)">Brand Design System</p>
    <h1 class="demo-display"><!-- INSERT BRAND NAME --></h1>
    <p class="demo-body" style="max-width: 480px; margin: var(--space-3) auto var(--space-6)"><!-- INSERT ONE-LINE DESCRIPTION FROM BRANDPACK --></p>
    <div class="btn-row" style="justify-content: center">
      <button class="btn btn-primary">Primary Action</button>
      <button class="btn btn-secondary">Secondary</button>
    </div>
  </div>

  <div class="section">
    <p class="section-label">Typography</p>
    <h1 class="demo-h1">Heading One — The quick brown fox</h1>
    <h2 class="demo-h2">Heading Two — Jumps over the lazy dog</h2>
    <h3 class="demo-h3">Heading Three — Subheading style</h3>
    <p class="demo-body">Body text at default size. The spacing, color, and line-height should feel comfortable for extended reading. This paragraph tests how the chosen body font renders at this weight and size.</p>
    <p class="demo-secondary" style="margin-bottom: var(--space-3)">Secondary text — captions, metadata, labels go here. Should be clearly less prominent than body text.</p>
    <p class="demo-label" style="margin-bottom: var(--space-2)">Label Style</p>
    <p class="demo-body">Inline <span class="demo-code">monospace code</span> in a sentence.</p>
  </div>

  <div class="section">
    <p class="section-label">Color Palette</p>
    <div class="color-grid">
      <div class="color-chip" style="background: var(--color-primary)" title="Primary"></div>
      <div class="color-chip" style="background: var(--color-secondary)" title="Secondary"></div>
      <div class="color-chip" style="background: var(--color-accent)" title="Accent"></div>
      <div class="color-chip" style="background: var(--color-background); border: 2px solid var(--color-border)" title="Background"></div>
      <div class="color-chip" style="background: var(--color-surface)" title="Surface"></div>
      <div class="color-chip" style="background: var(--color-surface-raised)" title="Surface Raised"></div>
      <div class="color-chip" style="background: var(--color-text-primary)" title="Text Primary"></div>
      <div class="color-chip" style="background: var(--color-text-secondary)" title="Text Secondary"></div>
      <div class="color-chip" style="background: var(--color-success)" title="Success"></div>
      <div class="color-chip" style="background: var(--color-warning)" title="Warning"></div>
      <div class="color-chip" style="background: var(--color-error)" title="Error"></div>
      <div class="color-chip" style="background: var(--color-info)" title="Info"></div>
    </div>
  </div>

  <div class="section">
    <p class="section-label">Buttons</p>
    <div class="btn-row">
      <button class="btn btn-primary">Primary</button>
      <button class="btn btn-secondary">Secondary</button>
      <button class="btn btn-ghost">Ghost</button>
      <button class="btn btn-destructive">Destructive</button>
      <button class="btn btn-disabled" disabled>Disabled</button>
    </div>
  </div>

  <div class="section">
    <p class="section-label">Cards & Elevation</p>
    <div class="card-grid">
      <div class="card">
        <h3 class="demo-h3" style="margin-bottom: var(--space-2)">Default Card</h3>
        <p class="demo-body" style="margin-bottom: var(--space-3)">This is a standard surface card with default shadow.</p>
        <p class="demo-secondary">Secondary metadata text</p>
      </div>
      <div class="card-raised">
        <h3 class="demo-h3" style="margin-bottom: var(--space-2)">Raised Card</h3>
        <p class="demo-body" style="margin-bottom: var(--space-3)">Elevated surface with higher shadow for emphasis.</p>
        <p class="demo-secondary">Secondary metadata text</p>
      </div>
    </div>
  </div>

  <div class="section">
    <p class="section-label">Form Elements</p>
    <div class="input-group">
      <label class="demo-label">Email address</label>
      <input class="demo-input" type="email" placeholder="you@example.com">
    </div>
    <div class="input-group">
      <label class="demo-label">Password</label>
      <input class="demo-input" type="password" placeholder="Enter your password">
    </div>
  </div>

  <div class="section">
    <p class="section-label">Status & Badges</p>
    <div class="status-row">
      <span class="badge badge-success">Success</span>
      <span class="badge badge-warning">Warning</span>
      <span class="badge badge-error">Error</span>
      <span class="badge badge-info">Info</span>
    </div>
  </div>

</div>
</body>
</html>
```

---

## Step 2 — Open in browser and evaluate

```bash
# Start the browse server if not already running
$B goto file:///tmp/brandpack-demo.html
$B screenshot /tmp/brandpack-check-desktop.png
$B responsive /tmp/brandpack-check
```

Show the user all three responsive screenshots (mobile, tablet, desktop).

---

## Step 3 — Visual quality checklist

Evaluate the rendered output against these questions:

**Color harmony:**
- Do the colors look good together? (not just technically correct — actually beautiful)
- Is there sufficient contrast between text and background?
- Does the accent color stand out appropriately without clashing?
- Does the palette feel cohesive, or like 12 unrelated colors?

**Typography:**
- Does the heading font look good at display size? Does it render cleanly?
- Is the heading/body pairing visually interesting? Or generic?
- Is body text comfortable to read at the chosen size?
- Does the type scale create clear hierarchy?

**Component feel:**
- Do the buttons look distinctive, or generic?
- Do the cards have appropriate visual weight?
- Does the spacing feel intentional or arbitrary?

**AI slop check:**
- Purple/blue gradient anywhere? → flag
- Everything the same border-radius? → flag
- Bright saturated primary with no depth? → flag
- Inter heading with no display face? → flag
- Colors that look like Tailwind defaults? → flag

**Responsive sanity:**
- Does the layout adapt cleanly on mobile?
- Is text readable at mobile size?
- Do touch targets look large enough?

---

## Step 4 — Iterate if needed

If any issues are found:
1. Identify which specific tokens need adjustment
2. Update the brandpack.md with improved values
3. Regenerate the demo HTML with the new values
4. Re-screenshot and verify

Only iterate a maximum of 2 times. If the output is still not beautiful after 2 iterations,
document the specific issues for the user to decide on manually.
