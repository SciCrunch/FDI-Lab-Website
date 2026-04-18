# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A static GitHub Pages website for the [FAIR Data Informatics Lab](https://fdilab.org) at UC San Diego. No build step, no framework, no package manager — just HTML files, one CSS file, and images. GitHub Pages serves the repo root directly from the `main` branch.

## Local preview

Open any `.html` file directly in a browser, or run a simple dev server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8080
```

There are no linting, build, or test commands.

## Site structure

```
/               → top-level pages (index, about, team, projects, funding, contact, tools)
/projects/      → one HTML file per project (bican, biccn, cinergi, d3r, dknet, fsci, nif, odc-sci, repronim, rrid, sparc, tara)
/css/style.css  → single stylesheet; all design tokens are CSS variables at the top
/images/        → site/, team/, and funding/ subdirectories
/fonts/         → self-hosted Oxygen font (woff2 files)
```

## Key conventions

**Navigation** — Every page duplicates the full `<header>` and `<footer>` blocks. The active page gets `class="active"` on its nav link. Top-level pages use relative paths (`href="projects.html"`); pages inside `projects/` use `../` prefixes (`href="../projects.html"`).

**CSS path** — Top-level pages: `css/style.css`. Project sub-pages: `../css/style.css`.

**Image/asset paths** — Same rule: top-level uses `images/…`, sub-pages use `../images/…`.

**Design tokens** — Colors, font stack in `:root` variables at the top of `style.css`. Use them (`var(--navy)`, `var(--accent)`, etc.) rather than hard-coding hex values.

**Page-scoped styles** — Pages add a `<style>` block in `<head>` for styles needed only on that page (e.g., `.project-card` on `projects.html`). Don't add single-page styles to the shared stylesheet.

**Project pages** — Each `projects/*.html` follows the same two-column layout: main content (About + FDI Lab Deliverables) on the left, a sidebar card (Details + FDI Lab Team) on the right. See `projects/bican.html` as the canonical template.

**Projects listing** — `projects.html` maintains two sections: **Active Projects** and **Past Projects**, each using `.project-card` with a `<span class="project-tag">` label. The homepage (`index.html`) shows active projects only as `.project-chip` links.

**No JavaScript framework** — The only JS on the site sets `document.getElementById('yr').textContent = new Date().getFullYear()` in the footer and toggles a `.open` class on `<nav>` for the mobile hamburger menu.

**Deployment** — Push to `main`. GitHub Pages deploys automatically from the repo root. There is no CI pipeline.
