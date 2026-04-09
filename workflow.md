# ProjectBased.AI — Workflow

## Site Map

| Page | File | Category | Status |
|------|------|----------|--------|
| Landing | `index.html` | — | Content complete, timeline + skills live |
| Theater & Immersive Arts | `theater.html` | Leading Teams... | Content complete, videos embedded, Featured In added |
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
- **Index page:** Static chapter list in hero right column; hamburger nav slides in on scroll past hero
- **Inner pages (theater, agency, interactive, ai-systems):** Hamburger menu (☰) with semi-transparent plum overlay, current page highlighted
- **experiential-knowledge.html:** Has its own dark-theme nav — do not modify

### Page Layout Pattern (inner pages)
- Page header with category label, title (left), and tagline (right) in a 2-column grid
- Two-column content area (sticky left, scrollable right)
- Impact/stats section with optional "Featured In" press row
- Throughline + "Next" link

### Index Page Layout
- Hero: name + gradient differentiator (left), chapter navigation (right), bouncing chevron scroll hint
- Timeline: alternating left/right entries (2007–2026) with milestone markers, staggered fade-in animations
- Skills block: hover-to-plum skill tags
- Contact bar

### Fonts
- **Light theme (all pages except experiential-knowledge):** Plus Jakarta Sans (200–800)
- **Dark theme (experiential-knowledge only):** Cormorant Garamond (serif) + DM Sans (sans)

### Color System
- **Light theme:** Background `#FAFAF8`, text `#1a1a1a`, accent plum `#5A2650`
- **Dark theme (experiential-knowledge):** Background `#070707`, text `#e8e4df`, accents gold `#c9a96e` + blue `#7a9bb5`
- **Key styling patterns:** Client names in plum, tagline `<em>` bold+italic+plum, section headers bold plum

---

## What's Done

- [x] Shared `styles.css` extracted from inline styles
- [x] Hamburger nav with plum overlay on all inner pages
- [x] Scroll-triggered hamburger nav on index page
- [x] Client logos on agency page (16 logos in `assets/CA Client logos/`)
- [x] Client names filled in on theater, interactive pages
- [x] Video embeds updated to new Vimeo account (theater page — 3 videos)
- [x] Video embed on interactive page (Vimeo)
- [x] AI systems page redesigned — full-width flip cards, plum front/light back
- [x] Page taglines added to theater, agency, interactive, ai-systems headers
- [x] Chapter numbers removed across all pages and menus
- [x] Front page: gray-to-plum gradient on differentiator, timeline (2007–2026), skills block
- [x] Section headers restyled (plum, bold, optically balanced)
- [x] "Featured In" press rows on theater (ABC, CNN, Streaming Media, The Verge) and agency (Fast Company, AdWeek, LA Times, Boston Globe)
- [x] Client names and capabilities styled in plum for quick scanning
- [x] Scroll hint: bouncing chevron, hero at 88vh for timeline peek
- [x] `site-copy.md` — all visible text extracted for review
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
- [ ] Add responsive handling for timeline on mobile

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

### Clean URLs
- `vercel.json` sets `cleanUrls: true` and `trailingSlash: false`
- Pages are reachable at extensionless paths (e.g. `/experiential-knowledge`), which is what OG/social meta tags and external forwards rely on

### insatiablemind.ai → experiential-knowledge
- Domain registered at Network Solutions, but forwarding is handled by **Cloudflare** (free plan), not NS
- Network Solutions nameservers point to Cloudflare (`stephane.ns.cloudflare.com`, `troy.ns.cloudflare.com`)
- Cloudflare SSL/TLS mode: **Full**, "Always Use HTTPS" on
- Cloudflare Redirect Rule ("Single Redirect") matches `http.host eq "insatiablemind.ai"` or `"www.insatiablemind.ai"` → 301 → `https://www.projectbased.ai/experiential-knowledge`
- Why not Network Solutions forwarding: NS forwarding is HTTP-only; its shared cert does not cover `insatiablemind.ai`, so modern browsers upgrading to HTTPS hit `ERR_CERT_COMMON_NAME_INVALID`. Cloudflare terminates TLS with a valid edge cert and performs the redirect at the edge.
- OG/Twitter image URLs in `experiential-knowledge.html` must point at `https://www.projectbased.ai/assets/...`, NOT `insatiablemind.ai/assets/...`, because the latter redirects to an HTML page and social platforms won't follow image-URL redirects

---

## Notes

- **experiential-knowledge.html** has its own design system — dark theme, different fonts, different color palette. Never modify its styling from shared CSS work.
- Page 5 has scroll-triggered reveal animations (JavaScript at bottom of file).
- Index page has scroll-triggered nav (JavaScript at bottom of file).
- Site is fully static — no server, no framework, no dependencies beyond Google Fonts.
- `site-copy.md` contains all visible text from all pages (except experiential-knowledge) for content review.
