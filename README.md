# terribledevice — V3 Design Mockup

> *Navigating the neon-lit alleys of pop culture.*

A static HTML design mockup for **terribledevice**, a cyberpunk/sci-fi pop culture criticism blog. V3 is the charcoal/teal/amber direction — warmer and more editorial than the other variants, closer to a critical journal than a game UI.

---

## Files

| File | Description |
|------|-------------|
| `terribledevice-v3-teal.html` | V3 homepage mockup — open directly in a browser |
| `terribledevice-v5-hybrid.html` | V5 hybrid mockup (magenta + amber) for A/B comparison |

---

## V3 Design Brief

### Palette

| Token | Hex | Role |
|-------|-----|------|
| `--charcoal` | `#1c2020` | Base background — warm dark, not pure black |
| `--teal` | `#22978d` | Primary accent — interactive states, screen pillar |
| `--teal-light` | `#2eb8ac` | Active labels, hover states, section headers |
| `--amber` | `#c8833a` | Secondary accent — CTAs, sound pillar, annotations |
| `--amber-light` | `#e0a050` | Highlight, wordmark gradient end |
| `--rust` | `#8b3520` | Interactive pillar, hero gradient bleed |
| `--text-primary` | `#dde8e6` | Body copy |
| `--text-secondary` | `#8aa09e` | Decks, excerpts, captions |
| `--text-dim` | `#4a5e5c` | Metadata, labels, manifest values |

### Typography

| Role | Font | Notes |
|------|------|-------|
| Wordmark | Zen Dots | Display only — amber → teal gradient treatment |
| UI / labels / nav | Orbitron 700–900 | All-caps, tracked, structural elements |
| Body / headlines | Barlow Condensed | 300–900 weight range; italic for decks and excerpts |
| Metadata / mono | Space Mono | Dates, word counts, manifest, tags |

### Hero Background

Layered radial gradients — no flat colours:
- Teal pool bleeding in from the top-right
- Rust/burnt orange bleeding from the bottom-left
- Subtle amber tint from above
- Sits over a `52px` teal grid at 5% opacity

### Layout Structure

```
┌─ sticky nav ──────────────────────────────────────────┐
├─ hero (2-col → 1-col on tablet) ──────────────────────┤
│  LEFT: featured essay + CTA                           │
│  RIGHT: 3 secondary article cards                     │
├─ main (1fr) ──────────────── sidebar (320px) ─────────┤
│  by pillar (3-col grid)    │  newsletter              │
│  editor's picks (3-col)    │  recent posts            │
│  recent list               │  tag index               │
│                            │  coordinates manifest    │
├─ status bar ──────────────────────────────────────────┤
└─ bottom ticker ───────────────────────────────────────┘
```

### Content Pillars

Each pillar has a dedicated accent colour used consistently across dots, labels, cards, and nav:

- **Screen** → teal
- **Sound** → amber
- **Interactive** → rust

### Interactive Details

- **HUD corner brackets** appear on article card hover (amber, 1px)
- **Sidebar posts** slide-indent on hover with teal title colour change
- **Tags** border and text shift to teal on hover
- **CTA buttons** fire a multi-stage glitch sequence on hover:
  - Diagonal shimmer sweep (`::before`)
  - Clip-path slice glitch (5-step keyframe, steps timing)
  - RGB split via coloured `box-shadow` offsets (teal left, rust right)
  - Teal noise bar flicker (`::after`)
- **Hero CTA** also runs a periodic idle glitch every 9 seconds unprompted

### Responsive Breakpoints

| Breakpoint | Changes |
|------------|---------|
| `≤ 1024px` | Hero collapses to single column; sidebar moves below content; pillar grid and editor's picks go single column; diagonal slash hidden |
| `≤ 768px` | Nav links hidden behind hamburger (animates to ✕ on open); hero secondary cards hidden; status bar right side hidden |
| `≤ 480px` | Tighter padding throughout; word counts hidden from article list; datecode watermark removed; CTA goes full width |

---

## Design References

- **The Designers Republic / Wipeout HUD** — dense information annotation, diagonal compositions, data-as-decoration
- **IDM / industrial sleeve art** — Autechre, Aphex Twin, early Warp Records
- **Cyberpunk UI lineage** — Ghost in the Shell, Akira, Blade Runner — filtered through editorial rather than game aesthetics

---

## Status

`DRAFT` — homepage mockup only. Next steps:

- [ ] Article page template (long-form reading column, pull quotes, hero treatment)
- [ ] Archive / index page
- [ ] Mobile nav refinements
- [ ] Real content integration
- [ ] CSS custom property theming (swap palettes via `:root` overrides)
