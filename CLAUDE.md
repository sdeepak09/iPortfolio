# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML5 portfolio website built on the BootstrapMade iPortfolio template. No build step, no package manager — static files are served directly.

- **Stack:** HTML5, CSS3, vanilla JavaScript, PHP (contact form only)
- **CSS Framework:** Bootstrap 5.3.2
- **Domain:** iportfolio.deepaksingh.app

## Development

**Local development:** Use the VS Code Live Server extension (configured on port 5501 in `.vscode/settings.json`), or any static file server.

There is no build, lint, or test command — this is a static site with no toolchain.

## Deployment

Deployment is automatic via GitHub Actions (Azure Static Web Apps). Pushing to `main` triggers the workflow in `.github/workflows/azure-static-web-apps-delightful-sea-05e06d200.yml`, which uploads the repo root directly (no build output step).

## Architecture

### Pages
- `index.html` — Main single-page portfolio (hero, about, skills, resume, portfolio, contact sections)
- `inner-page.html` — Secondary page template
- `portfolio-details.html` — Portfolio item detail view

### Key Files
- `assets/css/style.css` — All custom styles (overrides Bootstrap defaults)
- `assets/js/main.js` — All client-side behavior: navigation, scroll animations, typing effect, portfolio filtering, sliders, counters
- `forms/contact.php` — Contact form handler (requires PHP Email Form library; SMTP not configured)

### Vendor Libraries (in `assets/vendor/`)
AOS (scroll animations), Bootstrap + Bootstrap Icons, Boxicons, GLightbox (lightbox), Isotope (portfolio filtering), PureCounter (number counters), Swiper (carousels), Typed.js (typing animation), Waypoints (scroll triggers).

All vendor assets are committed directly — there is no package manager or CDN dependency.

### Images
Portfolio images, profile photos, and testimonial images live under `assets/img/`. This directory accounts for most of the repo size.
