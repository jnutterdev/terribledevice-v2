# SITE_BRIEF

## terribledevice // REV.02 // 2026

> _Navigating the neon-lit alleys of pop culture._

---

## 01 // CONCEPT

**terribledevice** is a pop culture blog anchored in cyberpunk and sci-fi, spanning film, music, and interactive media from the 1980s to the present. It's part criticism, part guided tour — written for the curious as much as the already-converted. If you've never seen the film or heard the record, that's fine. That's kind of the point.

The site sits at the intersection of two lineages:

- **The critical** — short takes, close readings, revisionist opinions, and excavations of overlooked work
- **The aesthetic** — a design language drawn from The Designers Republic, Wipeout HUD, IDM sleeve art, and the visual grammar of the very culture being written about

The design is not decoration. It is editorial position made visible.

---

## 02 // EDITORIAL

### Voice

Sharp, sardonic, occasionally very silly. Enthusiastic without being breathless. Treats pop culture as worth taking seriously without taking itself too seriously. Points at things and says _you should look at this_ — and then explains why, whether you've heard of it or not.

### Content Pillars

| Pillar          | Scope                                                     | Accent |
| --------------- | --------------------------------------------------------- | ------ |
| **Screen**      | Film, television, anime — anything that moves             | Teal   |
| **Sound**       | Music, soundtracks, electronic/experimental, IDM, ambient | Amber  |
| **Interactive** | Games, interactive fiction, software as cultural object   | Rust   |

### Era

1980s – present. The 1980s as origin point — Neuromancer, Blade Runner, Akira, early electronic music, the birth of the console era. Everything since as consequence, revision, or eulogy.

**Screen touchstones** — Blade Runner, Akira, Ghost in the Shell, RoboCop, Total Recall, Johnny Mnemonic, Nemesis, Split Second, Fortress, Strange Days, The Matrix, and the long tail of low-budget sci-fi that got there first and didn't get the credit.

**Sound touchstones** — anchored in IDM and glitch (Autechre, Richard Devine, Farmers Manual, Gridlock, Dryft, Huron, Subheim, Fennesz), with post-industrial threads (Haujobb, Forma Tadre), ambient (Fennesz, Access to Arasaka), and a lane for synthwave and retrowave that takes itself seriously (Perturbator, Mega Drive, Mitch Murder, Bourgeoisie). The connective tissue is a preoccupation with texture, machinery, and futures that feel handmade.

### Format

- **Posts** — primary format, short and focused, 300–800 words. One idea, well made.
- **Essays** — occasional longer pieces, 2,000–5,000 words, for when something demands the space
- **Revisits** — structured re-examinations of canonical works, dated and versioned

### Recurring Themes

- Cyberpunk as nostalgia — the genre that predicted the future now mourns it
- The city as protagonist — Neo-Tokyo, Night City, Los Angeles 2019
- Bodies, memory, and identity in posthuman fiction
- Afrofuturism and the politics of who gets to imagine the future
- Hauntology in electronic music — the ghost of futures that didn't arrive
- Failure states as narrative engines — games that use losing as meaning

---

## 03 // DESIGN SYSTEM

### Direction

The visual language is drawn from:

- **The Designers Republic** — dense information annotation, diagonal slash compositions, data as decoration, asymmetric grids
- **Wipeout HUD** — compressed Orbitron type, teal/amber contrast, HUD corner brackets, live indicator dots
- **IDM / industrial sleeve art** — Autechre, Aphex Twin, early Warp Records packaging
- **Cyberpunk UI lineage** — Ghost in the Shell, Akira, Blade Runner, filtered through editorial restraint rather than game aesthetics

The goal is a design system that looks like it was built by someone who owns the records and films being written about.

### Palette — V3 Charcoal/Teal/Amber

| Token              | Hex       | Role                                               |
| ------------------ | --------- | -------------------------------------------------- |
| `--charcoal`       | `#1c2020` | Base background — warm dark, not pure black        |
| `--charcoal-mid`   | `#222828` | Elevated surfaces, bottom ticker                   |
| `--charcoal-light` | `#2a3232` | Card backgrounds, column headers                   |
| `--teal`           | `#22978d` | Primary accent — Screen pillar, interactive states |
| `--teal-light`     | `#2eb8ac` | Active labels, hover states, section headers       |
| `--teal-dim`       | `#155f5a` | Borders, rule lines, dimmed teal elements          |
| `--amber`          | `#c8833a` | Secondary accent — Sound pillar, CTAs, annotations |
| `--amber-light`    | `#e0a050` | Highlights, wordmark gradient, hover titles        |
| `--amber-dim`      | `#7a4f22` | Dimmed amber borders, bottom ticker rule           |
| `--rust`           | `#8b3520` | Interactive pillar, hero gradient bleed            |
| `--text-primary`   | `#dde8e6` | Body copy                                          |
| `--text-secondary` | `#8aa09e` | Decks, excerpts, italic passages                   |
| `--text-dim`       | `#4a5e5c` | Metadata, manifest rows, word counts               |
| `--rule`           | `#2a3636` | Borders, dividers, grid lines                      |

### Typography

| Role             | Font             | Weight   | Usage                                                       |
| ---------------- | ---------------- | -------- | ----------------------------------------------------------- |
| Wordmark         | Zen Dots         | 400      | Display only — amber → teal gradient                        |
| UI / structural  | Orbitron         | 700, 900 | Nav, labels, pillar headers, tags, CTAs — all-caps, tracked |
| Editorial / body | Barlow Condensed | 300–900  | Headlines, body copy, excerpts — italic for decks           |
| Metadata         | Space Mono       | 400, 700 | Dates, word counts, manifest, mono annotations              |

### Hero Background

Layered radial gradients — no flat fills:

- Teal pool bleeding in from top-right (`30%` opacity)
- Rust/burnt orange bleeding from bottom-left (`40%` opacity)
- Subtle amber tint from above (`8%` opacity)
- `52px` teal grid overlay at `5%` opacity
- Diagonal slash divider: teal → amber gradient, `skewX(-8deg)`, `4px` wide

### Layout Structure

```
┌─ sticky nav (56px) ───────────────────────────────────────────┐
│  wordmark | SCREEN · SOUND · INTERACTIVE · ARCHIVE · ABOUT   │
│           |                                          REV.02   │
├─ hero (min 500px) ────────────────────────────────────────────┤
│  LEFT: featured essay title, deck, meta, CTA                  │
│  RIGHT: 3 secondary article cards with HUD corners            │
├─ main content (1fr) ──────────── sidebar (320px) ─────────────┤
│  By Pillar (3-col grid)        │  Transmission (newsletter)  │
│  Editor's Picks (3-col strip)  │  Recent Transmissions       │
│  Recent (numbered list)        │  Index (tag cloud)          │
│                                │  Coordinates (manifest)     │
├─ status bar (36px) ───────────────────────────────────────────┤
│  LIVE · LAST UPDATED · ENTRIES │  BUILD · PALETTE            │
└─ bottom ticker ───────────────────────────────────────────────┘
```

### Structural Components

**Navigation**

- Sticky, `56px`, `rgba(28,32,32,0.97)` with `backdrop-filter: blur(12px)`
- Wordmark in Zen Dots with amber → teal gradient
- Pillar links with coloured dot indicators
- `REV.02 // 2026` meta label (desktop only)
- Hamburger on mobile (animates to ✕, dropdown below nav)

**Article Cards**

- Pillar label (Orbitron, 8px, colour-coded)
- Title (Barlow Condensed 700)
- Excerpt (Barlow Condensed 300 italic)
- Metadata row (Space Mono 8px)
- Amber HUD corner brackets appear on hover

**Manifest Block**

- Sidebar component — reads like a file manifest or system readout
- Space Mono throughout, teal values on dim keys
- Fields: DESIGNATION / REVISION / FOCUS / ERA / PALETTE / ENTRIES / STATUS

**Bottom Ticker**

- Continuous scrolling strip, `55s` loop
- Charcoal-mid background, amber-dim top border
- Space Mono 10px, dim text, amber-dim bold labels
- Content: pillar headers + canonical title list

### Interactive Details

**CTA Glitch (hero button + newsletter button)**
On hover, a multi-stage sequence fires:

1. Diagonal shimmer streak sweeps left → right (`::before`, `0.38s`)
2. Clip-path slice glitch — 5-step keyframe, `steps(1, end)` timing, horizontal bands shift left/right
3. RGB split via coloured `box-shadow` offsets — teal left, rust right
4. Teal noise bar (`::after`) flickers at random vertical positions

Hero CTA also runs a **periodic idle glitch** every `9s` unprompted — clip-path slices + coloured shadows — then snaps clean.

**Hover states throughout**

- Article cards: teal background tint + amber HUD corners
- Sidebar posts: `6px` left indent slide + amber title colour
- Tags: teal text + teal-dim border
- Nav links: amber-light colour shift

### Responsive Breakpoints

| Breakpoint | Changes                                                                                                                                                         |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `≤ 1024px` | Hero collapses to single column (teal rule between panels); sidebar moves below content; pillar grid and editor's picks go single column; diagonal slash hidden |
| `≤ 768px`  | Nav links hidden behind hamburger; hero secondary cards hidden; `REV.02` meta hidden; status bar right side hidden; hero type scales down                       |
| `≤ 480px`  | Tighter padding throughout; word counts hidden from article list; datecode watermark removed; CTA goes full width                                               |

---

## 04 // CONTENT STRATEGY

### Newsletter — _Transmission_

Primary retention mechanism. Positioned in the sidebar above all other secondary content. Copy: _"New essays, signal-boosted links, and the occasional dispatch from the neon-lit edges of pop culture. No noise."_ Amber CTA with glitch effect on hover.

### Tagging

Flat taxonomy — no categories beyond the three pillars. Tags are thematic and cross-pillar: `cyberpunk`, `sci-fi`, `IDM`, `anime`, `game design`, `afrofuturism`, `ambient`, `transhumanism`, `noir`, `retrowave`, `hauntology`, `worldbuilding`, `AI`, `80s`.

### Metadata displayed per article

- Pillar (colour-coded)
- Date (ISO format — `2026-03-28`)
- Author
- Word count
- Read time (hero featured only)

---

## 05 // VARIANT HISTORY

| Version   | Palette                       | Notes                                           |
| --------- | ----------------------------- | ----------------------------------------------- |
| V1        | Void / cyan                   | TDR-strict dark; first layout pass              |
| V2        | Slate / orange                | Industrial print; only light-background variant |
| V3        | Charcoal / teal / amber       | **Current direction** — warm, editorial, mature |
| V4        | Magenta-black / yellow / teal | Cyberpunk 2077 UI lineage; aggressive           |
| V5 Hybrid | Magenta base / amber accent   | V4 energy + V3 warmth; strong alternative       |

V3 chosen as primary direction: editorial maturity over genre-obvious aggression. The brief's voice — sharp, sardonic, deeply knowledgeable — maps to V3's temperature. V5 remains a strong alternative if a harder visual stance is preferred.

---

## 06 // NEXT STEPS

- [ ] Article page template — long-form reading column, hero treatment, pull quotes, footnotes
- [ ] Archive / index page — filterable by pillar and tag
- [ ] About page — editorial statement, contributor bios
- [ ] Mobile nav refinements — consider pill-style pillar switcher on small screens
- [ ] Real content integration — first 3–5 essays
- [ ] CSS custom property theming — palette swap via `:root` override for future variant testing
- [ ] Performance pass — font subsetting, critical CSS, lazy load
- [ ] Accessibility audit — contrast ratios, focus states, screen reader structure

---

## 07 // REFERENCES

### Visual

- The Designers Republic (Sheffield, 1986–) — information design as aesthetic system
- Wipeout series UI (Psygnosis / SCEE, 1995–2012)
- Warp Records packaging — Autechre, Aphex Twin, LFO
- Ghost in the Shell (Oshii, 1995) — interface design, HUD overlays
- Blade Runner (Scott, 1982) — colour temperature, noir + neon
- Akira (Otomo, 1988) — urban density, type at scale

### Editorial

- _Sight & Sound_ — critical rigour as model
- _The Wire_ — music criticism that takes genre seriously
- _Frieze_ — art criticism voice applied to pop culture objects
- _Hyperdub / Fact Magazine_ — electronic music criticism lineage

---

_SITE_BRIEF // REV.02 // terribledevice // 2026_
