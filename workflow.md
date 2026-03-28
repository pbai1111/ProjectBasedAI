# ProjectBased.AI — Workflow

## Site Map

| Page | File | Chapter | Status |
|------|------|---------|--------|
| Landing | `index.html` | — | Content complete |
| Theater & Immersive Arts | `theater.html` | 01 | Video placeholders pending |
| Digital Media Agency | `agency.html` | 02 | Client + video placeholders pending |
| Live Interactive Production | `interactive.html` | 03 | Client + video placeholders pending |
| AI Production & Systems | `ai-systems.html` | 04 | Content complete |
| Experiential Knowledge Design | `experiential-knowledge.html` | 05 | Separate design system (InsatiableMind) — do not touch styling |

---

## Content Placeholders

### Client Names — Page 2 (agency.html)
- [ ] **Selected Clients list** (line 128–139): 8 × `[Client Name]` need real names
- [ ] **Work item #2** (line 180): Covid Response Video Campaign — `[Client]`
- [ ] **Work item #4** (line 198): The Million Voters Project — `[Client]`
- [ ] **Work item #5** (line 205–208): Entire card — `[Project Title]`, `[Project Type]`, `[Client]`

### Client Names — Page 3 (interactive.html)
- [ ] **Selected Clients list** (line 172–183): 8 × `[Client Name]` need real names
- [ ] **Work item #6** (line 266–268): Entire card — `[Project Title]`, `[Project Type]`, `[Client]`

### Video Embeds — Pages 1–3
Will eventually be YouTube/Vimeo iframes replacing current placeholder markup.

- [ ] **Page 1 (theater.html)**: 4 video placeholders
  - NBC Feature — Joanna Stern
  - WiredArts Fest Trailer
  - Education Program Trailer
  - Fathom Events — Live Play
- [ ] **Page 2 (agency.html)**: 5 work items with `Image / Video` thumbnail placeholders
- [ ] **Page 3 (interactive.html)**: 6 work items with `Image / Video` thumbnail placeholders

---

## Development Checklist

### Code Quality
- [ ] Extract shared CSS variables and resets into a `styles.css` (currently duplicated across all 5 pages)
- [ ] Extract shared nav/layout styles into the shared stylesheet
- [ ] Add `<meta name="description">` tags to each page for SEO
- [ ] Add Open Graph / social meta tags
- [ ] Add favicon
- [ ] Audit and fix any accessibility issues (alt text, ARIA labels, semantic HTML)
- [ ] Test all inter-page navigation links
- [ ] Test responsive layouts on mobile / tablet breakpoints

### Design Polish
- [ ] Verify consistent spacing and typography across pages 1–4
- [ ] Ensure hover states and transitions work consistently
- [ ] Check that contact email link at bottom of index.html resolves correctly (currently uses Cloudflare email obfuscation path)

### Performance
- [ ] Optimize Google Fonts loading (preconnect, font-display)
- [ ] Consider self-hosting Plus Jakarta Sans to reduce external dependency
- [ ] Add loading states for future video embeds

---

## Deployment Setup

### 1. Initialize Git Repository
```bash
cd /Users/kathryn/projects/ProjectBasedSite/projectbased-site
git init
git add .
git commit -m "Initial commit — static portfolio site"
```

### 2. Create GitHub Repository
```bash
gh repo create projectbased-site --public --source=. --push
```
Or create via GitHub UI, then:
```bash
git remote add origin git@github.com:USERNAME/projectbased-site.git
git push -u origin main
```

### 3. Connect to Vercel
- Go to [vercel.com](https://vercel.com) → New Project → Import Git Repository
- Select the `projectbased-site` repo
- Framework preset: **Other** (static HTML, no build step)
- Output directory: `.` (root)
- Deploy

### 4. Custom Domain (optional)
- In Vercel project settings → Domains → Add `projectbased.ai`
- Update DNS records as Vercel instructs

---

## Content Tracker

| Content Type | Where | What's Needed | Priority |
|-------------|-------|---------------|----------|
| Client names | agency.html | 8 selected clients + 2 work item clients | High |
| Client names | interactive.html | 8 selected clients | High |
| Work items | agency.html | 1 full card (title, type, client) | Medium |
| Work items | interactive.html | 1 full card (title, type, client) | Medium |
| Video URLs | theater.html | 4 YouTube/Vimeo embed URLs | Medium |
| Video/image assets | agency.html | 5 thumbnail images or video embeds | Medium |
| Video/image assets | interactive.html | 6 thumbnail images or video embeds | Medium |
| Contact email | index.html | Verify email link works outside Cloudflare | Low |

---

## Notes

- **Page 5 (experiential-knowledge.html)** has its own design system — dark theme, different fonts, different color palette. Style changes to pages 1–4 should never bleed into page 5.
- All CSS is currently embedded in each HTML file's `<style>` tag. No external stylesheets, no build tools.
- No JavaScript on pages 1–4. Page 5 likely has scroll-triggered animations.
- Site is fully static — no server, no framework, no dependencies.
