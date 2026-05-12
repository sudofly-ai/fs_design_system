# How to design for FutureStack

This is the operator's manual — follow it when creating any new design for FutureStack (landing page section, email, deck, ad, internal tool).

---

## Step 0 — Always start here

1. **Read `README.md`** for brand positioning and principles.
2. **Import `colors_and_type.css`** in your HTML file. One line, every token comes with it.
3. **Scope the surface with `.fs-scope`** on `<body>` or the top-level container so base styles do not leak into host applications.
4. **Open `kit.html`** in a second tab. It's the specimen page — copy-paste components from there instead of rewriting them.

```html
<link rel="stylesheet" href="colors_and_type.css">
<body class="fs-scope fs-bg-mesh">
```

---

## Step 1 — Decide the temperature of the page

Every FutureStack surface leans one of three ways. Pick one and stay there:

| Mode | Background | Use for |
|---|---|---|
| **Calm / corporate** | Flat `--fs-bg` + hairline grid via `.fs-bg-grid` | Docs, pricing, changelogs, settings |
| **Energetic / marketing** | `.fs-bg-mesh` (radial cyan/magenta/purple blobs) | Heroes, feature pages, CTAs, launch posts |
| **Technical / dev-focused** | `.fs-bg-grid` with a single glow accent | Integration pages, API copy, terminal-style demos |

Do NOT mix mesh + grid + glow all at once — it turns into visual noise.

---

## Step 2 — Lay out with a clear hierarchy

Every FutureStack section is three ingredients, in order:

1. **Eyebrow** — mono, uppercase, cyan. One to four words. (`.fs-eyebrow`)
2. **Headline** — Title Case, Inter 600–700, `--fs-size-3xl` or larger. Keep to one line if possible. (`.fs-h1` / `.fs-h2`)
3. **Lead** — `--fs-text-muted`, `--fs-size-md`, max 2 sentences. (`.fs-lead`)

```html
<p class="fs-eyebrow">// Integrations</p>
<h2 class="fs-h2">Works With <span class="fs-text-gradient">Your Favorite Tools</span></h2>
<p class="fs-lead">One backend, every frontend. Ship in Lovable today, Webflow tomorrow.</p>
```

**The gradient span applies to one phrase per headline — never the whole line.**

---

## Step 3 — Pick ONE primary action

Every surface has exactly one magenta button (`.fs-btn-primary`). Secondary actions use `.fs-btn-secondary` (cyan-outline-on-hover). Ghost buttons are for tertiary nav only.

```html
<a class="fs-btn fs-btn-primary fs-btn-lg">Start Free →</a>
<a class="fs-btn fs-btn-secondary fs-btn-lg">Schedule a Demo</a>
```

If you find yourself writing a second magenta CTA on a page, something is wrong — consolidate or demote.

---

## Step 4 — Numbers are first-class

FutureStack sells on concrete stats: `$0.24`, `10x faster`, `500+ integrations`. Treat numbers as display elements:

- Use `--fs-size-4xl` or larger.
- Font weight 700.
- Optional: wrap in `.fs-text-gradient` for the headline stat.
- Always pair with a short mono label underneath (`.fs-mono`, uppercase, subtle).

Do NOT invent stats. Pull from the source of truth (React_Source copy) or leave a placeholder.

---

## Step 5 — Pick your card

Five card patterns exist; re-use them rather than inventing:

| Pattern | When |
|---|---|
| **`.fs-card`** (solid surface) | Feature lists, pricing rows, settings |
| **`.fs-glass`** (blurred panel) | Floating on hero, modals, dropdowns |
| **Stat card** (big number + label) | Social proof, metrics strips |
| **Feature card** (icon + title + body) | "How it works", feature grids |
| **Pricing card** (+ optional gradient border for "Most Popular") | Pricing tables |

All live in `kit.html` — copy from there.

---

## Step 6 — Glow is a feature, not decoration

Use a glow only to:
- Mark the primary CTA (magenta glow — already on `.fs-btn-primary`).
- Mark a live/active state (pulsing cyan via `.fs-animate-pulse`).
- Highlight the "Most Popular" pricing tier (magenta shadow on the card).

Do not glow every card, every icon, every heading.

---

## Step 7 — Imagery & iconography

- **Brand artwork:** prefer `hero-image.png` (isometric network) or `hero-sphere.png` (logo orb) rather than drawing new SVGs. If you must draw, mimic the isometric cube / data-flow metaphor — never invent mascots.
- **Icons:** use [Lucide](https://lucide.dev) (matches the React source). Load from CDN:
  ```html
  <script src="https://unpkg.com/lucide@latest"></script>
  <script>lucide.createIcons()</script>
  ```
- **No emoji.** Ever. Even in "fun" contexts.
- **No stock photography of people** unless explicitly customer-supplied.

---

## Step 8 — Copy voice

- **Headlines:** Title Case. `Works With Your Favorite Tools`, not `Works with your favorite tools`.
- **Buttons:** imperative + specific. `Start Free`, `Schedule a Demo`, `Connect Lovable` — not `Click here`, `Learn more`.
- **Body:** short sentences. Lead with the benefit, prove with a number.
- **Technical terms** (API, CMS, webhook, endpoint) stay in `.fs-mono` when inline.

---

## Step 9 — Before you ship, verify

Run this mental checklist:

- [ ] Background temperature is ONE mode (calm, energetic, or technical).
- [ ] Page has exactly one `.fs-btn-primary`.
- [ ] The text gradient is applied to one phrase, not the whole headline.
- [ ] Every stat has a mono label below it.
- [ ] No emoji, no stock photos, no invented icons.
- [ ] Minimum font size is 14px (12px only for `.fs-eyebrow` / `.fs-micro`).
- [ ] Hover states exist on every interactive element.
- [ ] `prefers-reduced-motion` is respected (handled automatically if you use `.fs-animate-*`).

---

## Anti-patterns — do NOT do these

❌ Full-page gradient backgrounds (reserved for specific hero blocks)
❌ Rounded-corner containers with a left-border accent color (generic SaaS slop)
❌ Stacking three glows on adjacent elements
❌ Using magenta for both CTAs and body-text highlights
❌ Inter for stats (use mono or gradient display)
❌ System emoji in place of real icons
❌ Light-mode surfaces (FutureStack is dark-native)
❌ Drawing the logo — always use `/assets/futureproof-icon.png`

---

*When in doubt, look at `kit.html`. When still in doubt, ask.*
