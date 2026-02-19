# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **al-folio** Jekyll-based academic website for matthewrobertballard.com. It generates a static site with publications, teaching, projects, news, and blog sections.

## Build & Development Commands

```bash
bundle install                    # Install Ruby dependencies
bundle exec jekyll serve          # Local dev server at http://localhost:4000
bundle exec jekyll build          # Build site (outputs to ../website per _config.yml)
./bin/deploy                      # Deploy to GitHub Pages (gh-pages branch)
```

Note: The `destination` in `_config.yml` is set to `../website`, so builds output one directory up.

## Architecture

**Jekyll static site generator** with these key layers:

- **`_config.yml`** — Central configuration: site metadata, plugin settings, feature flags, library versions, Jekyll Scholar bibliography config. Most site-wide changes start here.
- **`_layouts/`** — Page templates. `default.html` is the base; `about.html` is the homepage; `bib.html` handles bibliography detail pages.
- **`_includes/`** — Reusable HTML partials (header, footer, social links, scripts). `_includes/scripts/` contains JS integration (MathJax, jQuery, etc.).
- **`_pages/`** — Static content pages (about.md, publications.md, teaching.md, etc.).
- **`_bibliography/papers.bib`** — BibTeX file processed by `jekyll-scholar` plugin. This drives the publications page. Coauthor linking is configured via `_data/coauthors.yml`.
- **`_sass/`** — SCSS stylesheets. `_variables.scss` for theme colors, `_themes.scss` for dark/light mode, `_base.scss` and `_layout.scss` for core styles.
- **`_news/`** — Announcement items (output: true, generates individual pages).
- **`_projects/`** — Project entries (output: false, displayed inline only).
- **`_posts/`** — Blog posts in standard Jekyll format.
- **`assets/`** — Static files: images, PDFs, CSS, JS.

## Key Plugins

- **jekyll-scholar** — Bibliography/citation processing from BibTeX (APA style)
- **jekyll-paginate-v2** — Blog pagination
- **jekyll-feed** / **jekyll-sitemap** — RSS and sitemap generation
- **jemoji** — GitHub emoji support
- **jekyll-email-protect** — Email address obfuscation

## Content Editing Patterns

- **Publications**: Edit `_bibliography/papers.bib` (BibTeX format). Link coauthors via `_data/coauthors.yml`.
- **Pages**: Edit markdown files in `_pages/`. Front matter controls layout, title, permalink.
- **News**: Add dated markdown files to `_news/` (format: `_news/announcement_N.md`).
- **Site metadata/social links**: Update `_config.yml` (social section, scholar section, etc.).
- **CV**: Replace `assets/pdf/ballard_cv.pdf`.

## Deployment

- Source branch: `master`
- Deploy branch: `gh-pages`
- GitHub Actions workflow (`.github/workflows/deploy.yml`) builds and deploys on push to master
- Uses Ruby 2.7 in CI

## Enabled Features

MathJax (LaTeX math), Google Analytics, dark mode, Masonry layout, medium-style image zoom. Bootstrap 4.5.2 base styling.
