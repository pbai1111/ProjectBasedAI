# ProjectBased.AI

Portfolio site for Kathryn Jones — 15+ years leading teams at the intersection of technology and creativity, now applied AI.

## Tech Stack

- Static HTML/CSS — no framework, no build step
- Google Fonts (Plus Jakarta Sans, Cormorant Garamond, DM Sans)
- Vimeo embeds for video
- Hosted on Vercel

## Site Structure

```
index.html                  Landing page
theater.html                Theater & Immersive Arts
agency.html                 Digital Media Agency
interactive.html            Live Interactive Production
ai-systems.html             AI Video Production & Creative Workflows
experiential-knowledge.html Experiential Knowledge Design (separate dark theme)
styles.css                  Shared stylesheet (light theme pages)
assets/                     Images, audio, video, client logos
workflow.md                 Internal development notes
```

## Local Development

No build tools required. Open any HTML file directly in a browser, or run a local server:

```bash
npx serve .
```

## Deployment

Static site deployed to Vercel from the `main` branch. No build command, output directory is root (`.`).

## Design Notes

- Five light-theme pages share `styles.css` with page-specific overrides in small inline `<style>` blocks
- `experiential-knowledge.html` has its own complete dark-theme design system (different fonts, colors, animations) — do not modify through shared CSS
- Navigation on inner pages uses a hamburger menu with a semi-transparent plum overlay
