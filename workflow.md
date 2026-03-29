# ProjectBased.AI — Workflow

## Site Map

| Page | File | Category | Status |
|------|------|----------|--------|
| Landing | `index.html` | — | Content complete |
| Theater & Immersive Arts | `theater.html` | Leading Teams... | Content complete, videos embedded |
| Digital Media Agency | `agency.html` | Leading Teams... | Content complete, client logos live |
| Live Interactive Production | `interactive.html` | Leading Teams... | Content complete, video embedded |
| AI Video Production & Creative Workflows | `ai-systems.html` | Applied AI | Content complete, flip cards live |
| Experiential Knowledge Design | `experiential-knowledge.html` | — | Separate design system (InsatiableMind) — do not touch styling |

---

## Architecture

### Shared Styles
- **`styles.css`** — Single shared stylesheet containing CSS variables, reset, nav, layout, typography, impact sections, throughline, video/work items, contact bar, responsive breakpoints
- Each page links `styles.css` and uses a small inline `<style>` block for page-specific overrides only
- **Exception:** `experiential-knowledge.html` has its own complete dark-theme `<style>` block (different fonts, colors, variables) that overrides `styles.css`

### Navigation
- **Index page:** Static chapter list in the hero right column
- **Inner pages (theater, agency, interactive, ai-systems):** Hamburger menu (☰) with semi-transparent plum overlay, current page highlighted
- **experiential-knowledge.html:** Has its own dark-theme nav — do not modify

### Page Layout Pattern (inner pages)
- Page header with category label, title (left), and tagline (right) in a 2-column grid
- Two-column content area (sticky left, scrollable right)
- Impact/stats section
- Throughline + "Next" link

### Fonts
- **Light theme (all pages except experiential-knowledge):** Plus Jakarta Sans (200–800)
- **Dark theme (experiential-knowledge only):** Cormorant Garamond (serif) + DM Sans (sans)

### Color System
- **Light theme:** Background `#FAFAF8`, text `#1a1a1a`, accent plum `#5A2650`
- **Dark theme (experiential-knowledge):** Background `#070707`, text `#e8e4df`, accents gold `#c9a96e` + blue `#7a9bb5`

---

## What's Done

- [x] Shared `styles.css` extracted from inline styles
- [x] Hamburger nav with plum overlay on all inner pages
- [x] Client logos on agency page (16 logos in `assets/CA Client logos/`)
- [x] Client names filled in on theater, interactive pages
- [x] Video embeds updated to new Vimeo account (theater page — 3 videos)
- [x] Video embed on interactive page (Vimeo)
- [x] AI systems page redesigned — full-width flip cards, plum front/light back
- [x] Page taglines added to theater, agency, interactive, ai-systems headers
- [x] Chapter numbers removed across all pages and menus
- [x] Front page gradient (gray → plum) on differentiator text
- [x] Section headers restyled (plum, bold, optically balanced)
- [x] Git repo on GitHub, pushed to main

---

## Development Checklist

### Still To Do
- [ ] Add `<meta name="description">` tags to each page for SEO
- [ ] Add Open Graph / social meta tags
- [ ] Add favicon
- [ ] Audit accessibility (alt text on logos, ARIA labels, semantic HTML)
- [ ] Test all inter-page navigation links
- [ ] Test responsive layouts on mobile / tablet breakpoints
- [ ] Verify contact email link on index.html works
- [ ] Add responsive handling for page-header tagline grids (mobile stacking)

### Performance
- [ ] Optimize Google Fonts loading (preconnect, font-display)
- [ ] Consider self-hosting Plus Jakarta Sans
- [ ] Optimize logo image sizes (some are large originals)

---

## Deployment

### Current Setup
- Git repo: `https://github.com/pbai1111/ProjectBasedAI.git`
- Branch: `main`
- Static HTML — no build step, no framework

### Vercel Deployment
- Go to [vercel.com](https://vercel.com) → New Project → Import Git Repository
- Select the `ProjectBasedAI` repo
- Framework preset: **Other** (static HTML, no build step)
- Output directory: `.` (root)
- Deploy

### Custom Domain
- In Vercel project settings → Domains → Add `projectbased.ai`
- Update DNS records as Vercel instructs

---

## Notes

- **experiential-knowledge.html** has its own design system — dark theme, different fonts, different color palette. Never modify its styling from shared CSS work.
- Page 5 has scroll-triggered reveal animations (JavaScript at bottom of file).
- Site is fully static — no server, no framework, no dependencies beyond Google Fonts.
- The `experiential-knowledge_base64_backup.html` file has been removed from the project.
