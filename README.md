# terribledevice — Design Mockup

> _Navigating the neon-lit alleys of pop culture._

A static HTML design mockup for **terribledevice**, a cyberpunk/sci-fi pop culture blog. V3 (charcoal/teal/amber) is the chosen design direction — warm, editorial, closer to a critical journal than a game UI.

---

## Files

| File                                     | Description                               |
| ---------------------------------------- | ----------------------------------------- |
| `terribledevice-v2.3-teal.html`          | V3 homepage — primary direction           |
| `terribledevice-v2.3-article.html`       | Article page template                     |
| `terribledevice-v2.3-archive.html`       | Archive / index page with working filters |
| `terribledevice-v2.3-about.html`         | About page                                |
| `terribledevice-v2.3-teal-original.html` | V3 original (pre-refinement reference)    |
| `terribledevice-v2.4-magenta.html`       | V4 magenta/yellow variant (A/B reference) |
| `terribledevice-v2.5-hybrid.html`        | V5 hybrid — magenta base + amber accent   |
| `SITE_BRIEF.md`                          | Full editorial and design brief           |
| `README.md`                              | This file                                 |

---

## Tech Stack

| Layer         | Choice                       | Notes                                                           |
| ------------- | ---------------------------- | --------------------------------------------------------------- |
| **Framework** | [Astro](https://astro.build) | Static site generation, content collections, zero JS by default |
| **CMS**       | [Tina CMS](https://tina.io)  | Git-backed content management, visual editing                   |
| **Hosting**   | Self-hosted (Apache)         | Own server, full control                                        |
| **CI/CD**     | GitHub Actions               | Build and deploy on push to `main`                              |

### Why Astro

Content-first, fast by default, and the component model maps cleanly onto the design system already built in the mockups. Content Collections will handle the three pillars (Screen / Sound / Interactive) as typed schemas.

### Why Tina CMS

Git-backed — content lives in the repo as Markdown, no external database. Visual editing layer for writing posts without touching code. Works well with Astro's content collections.

### Deployment Flow

```
push to main
  → GitHub Actions triggers
  → Astro build (npm run build)
  → rsync / scp dist/ to Apache server
  → Apache serves static files
```

---

## V3 Design System

### Palette

| Token              | Hex       | Role                                               |
| ------------------ | --------- | -------------------------------------------------- |
| `--charcoal`       | `#1c2020` | Base background — warm dark, not pure black        |
| `--teal`           | `#22978d` | Primary accent — Screen pillar, interactive states |
| `--teal-light`     | `#2eb8ac` | Active labels, hover states, section headers       |
| `--amber`          | `#c8833a` | Secondary accent — Sound pillar, CTAs, annotations |
| `--amber-light`    | `#e0a050` | Highlights, wordmark gradient, hover titles        |
| `--rust`           | `#8b3520` | Interactive pillar, hero gradient bleed            |
| `--text-primary`   | `#dde8e6` | Body copy                                          |
| `--text-secondary` | `#8aa09e` | Decks, excerpts, italic passages                   |
| `--text-dim`       | `#4a5e5c` | Metadata, labels, manifest values                  |
| `--rule`           | `#2a3636` | Borders, dividers, grid lines                      |

### Typography

| Role             | Font             | Weight   | Usage                                                 |
| ---------------- | ---------------- | -------- | ----------------------------------------------------- |
| Wordmark         | Zen Dots         | 400      | Display only — amber → teal gradient                  |
| UI / structural  | Orbitron         | 700, 900 | Nav, labels, pillar headers, CTAs — all-caps, tracked |
| Editorial / body | Barlow Condensed | 300–900  | Headlines, body copy, excerpts — italic for decks     |
| Metadata         | Space Mono       | 400, 700 | Dates, word counts, manifest, annotations             |

### Content Pillars

| Pillar          | Accent | Scope                                      |
| --------------- | ------ | ------------------------------------------ |
| **Screen**      | Teal   | Film, television, anime                    |
| **Sound**       | Amber  | Music, IDM, electronic, ambient, synthwave |
| **Interactive** | Rust   | Games, interactive fiction                 |

### Responsive Breakpoints

| Breakpoint | Changes                                                                     |
| ---------- | --------------------------------------------------------------------------- |
| `≤ 1024px` | Hero single column; sidebar below content; pillar grid stacks; slash hidden |
| `≤ 768px`  | Hamburger nav; hero secondary cards hidden; status bar trimmed              |
| `≤ 480px`  | Tighter padding; word counts hidden; datecode removed; CTA full width       |

### Interactive Details

- **CTA glitch** — shimmer sweep + clip-path slice + RGB split box-shadow + noise bar on hover; hero CTA also fires an idle glitch every 9s
- **HUD corners** — amber L-brackets on article card hover
- **Sidebar posts** — 6px indent slide on hover
- **Hamburger** — animates to ✕ on open, closes on link click

---

## Next Steps

### Design

- [ ] Refine nav links across all pages (currently `#` placeholders on pillar links)
- [ ] 404 page
- [ ] Mobile nav pill-style pillar switcher

### Build

- [ ] Scaffold Astro project
- [ ] Set up Tina CMS content collections (one per pillar)
- [ ] Port design system to Astro component library
- [ ] Implement homepage, article, archive, and about page templates
- [ ] Configure GitHub Actions workflow for build + deploy to Apache
- [ ] Set up Apache vhost and SSL

### Content

- [ ] Real content integration — first 3–5 posts
- [ ] Newsletter integration (Buttondown / similar)

### Polish

- [ ] Font subsetting — reduce Orbitron and Zen Dots payload
- [ ] Accessibility audit — contrast ratios, focus states, screen reader structure
- [ ] Performance pass — critical CSS, image optimisation
