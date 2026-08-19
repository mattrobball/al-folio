# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## Project Overview

The **al-folio** Jekyll site for matthewrobertballard.com.

As of the v1.2 upgrade, al-folio is a **gem-based theme**. The theme's layouts,
includes, and styles are no longer vendored in this repo — they live in the
`al_folio_core` gem and its `al_*` companions (see `Gemfile`). This repo holds
site-owned content and configuration only.

## Build & Development

Requires a modern Ruby (installed via `brew install ruby`); the macOS system
Ruby is too old.

```bash
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
bundle install
bundle exec jekyll serve     # local dev server
bundle exec jekyll build     # builds to ./_site
```

Optional: `jupyter-nbconvert` on PATH is only needed for Jupyter notebook posts.

## Where things live

- **`_config.yml`** — all site settings. `theme: al_folio_core` wires in the theme.
- **`_data/socials.yml`** — social links, rendered by `jekyll-socials`. MathSciNet,
  zbMATH, and Math Genealogy are `custom_social` entries; the rest are built in.
- **`_data/coauthors.yml`** — coauthor linking for the bibliography.
- **`_bibliography/papers.bib`** — drives `/publications/` via jekyll-scholar.
  Years are grouped automatically (`group_by: year`); do **not** reintroduce a
  hardcoded `years:` list in `_pages/publications.md` — that silently drops papers
  from years missing off the list.
- **`_pages/`** — about, publications, teaching (plus 404, blog, news).
- **`_news/`** — news items, shown on the homepage and `/news/`.
- **`_projects/`** — project entries, currently `output: false` (unpublished).
  Flip the collection to `output: true` in `_config.yml` and move
  `_drafts/projects.md` into `_pages/` to publish them.
- **`assets/`** — images, CV PDF.

## Local theme overrides

Local files shadow theme files of the same path. Overrides are tracked in
`.al-folio-overrides.yml` so gem upgrades can flag drift.

Current overrides:
- `_layouts/about.liquid` — copy of the theme layout with a **funding** section
  added between news and selected publications. Driven by `funding: true` in
  `_pages/about.md` front matter and `_includes/funding.liquid`.

After upgrading gems, re-check overrides:

```bash
bundle exec al-folio upgrade audit --no-fail
bundle exec al-folio upgrade overrides audit
bundle exec al-folio upgrade overrides diff _layouts/about.liquid
bundle exec al-folio upgrade overrides accept _layouts/about.liquid
```

## Third-party scripts

Do not add third-party script tags to page templates. The pre-v1 site carried
`polyfill.io`, `extreme-ip-lookup.com` (JSONP, with a committed API key), and a
`gitcdn.link` stylesheet; all were removed. polyfill.io in particular was sold and
used to serve malware. Prefer the theme's own plugins over hand-rolled snippets.

## Content editing

- **Publications**: edit `_bibliography/papers.bib`.
- **News**: add a dated markdown file to `_news/`.
- **CV**: replace `assets/pdf/ballard_cv.pdf`.
- **Pages**: edit markdown in `_pages/`; front matter controls layout, title,
  permalink, and `nav`/`nav_order`.

`TODO.md` tracks outstanding content corrections.
