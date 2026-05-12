# FutureStack Design System

> The visual and interaction language for FutureStack — the AI-powered CMS backend for no-code builders.

FutureStack's identity is built around a simple tension: **the deep calm of a reliable backend** (deep navy, monospaced marks, grid structure) lit up by **the energy of AI and modern tooling** (cyan → magenta → purple gradients, pulsing glows, glass surfaces). This system captures both sides.

---

## 1. Brand at a glance

| | |
|---|---|
| **Product** | FutureStack — AI-Powered CMS for no-code builders (Drupal-based) |
| **Parent** | Sudofly LLC |
| **One-liner** | *"The AI-Powered CMS Backend Your No-Code Tools Need"* |
| **Audience** | Solo builders, agencies, and teams shipping with Lovable, Webflow, v0, Cursor, Framer |
| **Tone** | Confident, technical, punchy. Benefit-first. Comfortable with numbers. |
| **Voice** | Title-Case Headlines. Short Sentences. Let the Stats Breathe. |

---

## 2. What's in this system

```
colors_and_type.css     Foundational tokens — colors, type, radius, motion, spacing
01-foundations.html     Color palette, gradients, type scale, radius, shadow, motion
02-logo-and-icon.html   Brand mark, icon, clearspace, placement, don'ts
03-buttons.html         Button variants, sizes, states
04-chips-and-badges.html  Chips, pills, status dots
05-cards.html           Card patterns — glass, solid, stat, feature, pricing
06-forms.html           Inputs, textarea, select, checkbox, radio
07-navigation.html      Top nav, footer, breadcrumbs
08-hero-patterns.html   Hero compositions + background treatments
kit.html                Everything-in-one UI kit (specimen page)
SKILL.md                How to use this system when designing for FutureStack
```

Every consumer imports one file:

```html
<link rel="stylesheet" href="colors_and_type.css">
```

Tokens are exposed as CSS custom properties prefixed `--fs-*` and utility classes prefixed `fs-*` so they never collide with Tailwind or other systems.

---

## 3. Core principles

1. **Dark by default.** FutureStack lives on a deep navy (`#0D1B2A`). Light surfaces are the exception and always use glass (blur + low-alpha), never solid white.
2. **Gradients carry meaning.** The cyan → magenta text gradient is reserved for the product name and the single most important phrase in a view. Don't spray it.
3. **Glow is punctuation.** A magenta or cyan glow marks a call to action or a live/active state. Two glows compete; one glow commands.
4. **Mono = machinery.** JetBrains Mono is used for eyebrows, stats, technical labels, and pricing — anywhere we want the reader to feel the system underneath.
5. **Structure on structure.** Animated grid backgrounds, hex patterns, and isometric stacks are core brand furniture. Empty expanses of flat color are undercooked.
6. **One idea per surface.** A card holds one stat, one feature, or one quote. When in doubt, cut.

---

## 4. Quick reference — tokens

### Colors
| Token | Hex | Use |
|---|---|---|
| `--fs-bg` | `#0D1B2A` | Page background |
| `--fs-bg-sec` | `#0a1420` | Alt sections, footers |
| `--fs-surface` | `#1a1f2e` | Card / panel |
| `--fs-surface-2` | `#242a3d` | Raised / hover |
| `--fs-border` | `#2a3441` | Hairline |
| `--fs-cyan` | `#00D4FF` | Primary accent — info, links, active |
| `--fs-magenta` | `#E91E8C` | CTA, brand highlight |
| `--fs-purple` | `#7B2FFF` | Deep accent, gradient anchor |
| `--fs-coral` | `#FF6B4A` | Warmth, danger |
| `--fs-teal` | `#4FFFB0` | Success, positive stats |
| `--fs-text` | `#e6edf3` | Body text |
| `--fs-text-muted` | `#9ca3af` | Secondary text |

### Type
- **Display / UI:** Inter — 400, 500, 600 (body & UI) + **Space Grotesk** — 500, 600, 700 (headlines)
- **Mono:** JetBrains Mono — 400, 500, 700
- Scale: `xs 12` → `sm 14` → `base 16` → `md 18` → `lg 20` → `xl 24` → `2xl 32` → `3xl 40` → `4xl 56` → `5xl 72`

### Radius
`xs 2 · sm 4 (default) · md 8 (buttons) · lg 12 (cards) · xl 16 · full 9999`

### Motion
`fast 150ms · base 250ms · slow 400ms` — ease `cubic-bezier(0.2, 0.8, 0.2, 1)`

---

## 5. Quick reference — signature moves

| Move | Class | When |
|---|---|---|
| Glass panel | `.fs-glass` | Nav, floating panels, overlays |
| Magenta CTA | `.fs-btn-primary` | Single primary action per view |
| Cyan text accent | `.fs-text-gradient` | Product name, hero keyword |
| Mesh background | `.fs-bg-mesh` | Heroes, section dividers |
| Grid background | `.fs-bg-grid` | "Technical" sections, dev-focused |
| Float animation | `.fs-animate-float` | Hero artwork, isolated icons |
| Pulse glow | `.fs-animate-pulse` | "Live" indicators, active nodes |

---

## 6. How to design for FutureStack

See [`SKILL.md`](./SKILL.md) for the canonical recipe — when starting a new FutureStack design, read that first, then pull components from `kit.html`.

---

*Version 1.0 · Maintained alongside the marketing site (`/React_Source`).*
