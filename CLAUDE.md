# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal landing page / blog for [pccofvns.live](https://pccofvns.live), built with Jekyll and deployed via GitHub Pages (auto-deploys on push to `master`).

## Development Commands

No Gemfile is present — relies on GitHub Pages' default Jekyll environment. To run locally with the standard Jekyll gem:

```bash
jekyll serve        # Serve at http://localhost:4000
jekyll build        # Build to _site/
```

## Architecture

Single-page Jekyll site with a custom "compass" theme. Key pieces:

- **`_config.yml`** — All site configuration including theme skin (`turquoise` by default; options: turquoise, blue, green, berry, orange, ceramic), Google Analytics ID, and SASS settings.
- **`_layouts/default.html`** — Base HTML template. Wraps content through `_layouts/compress.html` for HTML minification.
- **`_includes/compass.html`** — Main content area rendered inside the layout.
- **`_includes/head.html`** — Meta tags, Open Graph / Twitter Card SEO, stylesheet/font links.
- **`assets/css/main.scss`** — SCSS entry point; imports `_sass/_base.scss` and the active skin from `_sass/skins/`.
- **`assets/js/main.js`** — jQuery skill-bar animation on page load (only JS behavior on the site).

## External Libraries (CDN)

All vendor libraries are loaded via CDN — there are no local copies in `assets/plugins/`. Current versions:

| Library | Version | CDN |
|---------|---------|-----|
| Bootstrap | 5.3.3 | jsDelivr (`cdn.jsdelivr.net/npm/bootstrap@5.3.3`) |
| Font Awesome | 6.7.2 | cdnjs (`cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2`) |
| jQuery | 3.7.1 | jquery.com (`code.jquery.com/jquery-3.7.1.min.js`) |
| Google Fonts (Vollkorn) | — | `fonts.googleapis.com/css2` |

jQuery and Bootstrap JS are loaded at the bottom of `_layouts/default.html`; CSS links are in `_includes/head.html`.

## Styling

SCSS lives in `_sass/`. The active skin is set via `theme_skin` in `_config.yml`. To add or change a skin, add a `_sass/skins/_<name>.scss` file and update the config. Output is compressed (`style: compressed` in `_config.yml`).

## Deployment

Push to `master` → GitHub Pages auto-builds and publishes. Custom domain is set via `CNAME` (pccofvns.live). The `_site/`, `.jekyll-metadata` directories are gitignored (build artifacts).
