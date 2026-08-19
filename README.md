# matthewrobertballard.com

Source for [matthewrobertballard.com](https://www.matthewrobertballard.com), built
with [Jekyll](https://jekyllrb.com) and the [al-folio](https://github.com/alshedivat/al-folio)
theme (v1.x, gem-based).

## Local development

Needs a modern Ruby — the macOS system Ruby is too old.

```bash
brew install ruby
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"

bundle install
bundle exec jekyll serve   # http://localhost:4000
```

`imagemagick` is required for responsive images; `jupyter-nbconvert` only if you
add Jupyter notebook posts.

## Editing

| What | Where |
| --- | --- |
| Publications | `_bibliography/papers.bib` |
| News | `_news/` |
| About / publications / teaching pages | `_pages/` |
| Social links | `_data/socials.yml` |
| CV | `assets/pdf/ballard_cv.pdf` |
| Site settings | `_config.yml` |

See [CLAUDE.md](CLAUDE.md) for architecture notes, the local theme override, and
the gem-upgrade checks. `TODO.md` tracks outstanding content corrections.
