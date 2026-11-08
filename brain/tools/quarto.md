# Quarto

The public website. Claude Code builds the site structure; Lucas writes the posts.

## Structure

| Path | What |
|---|---|
| `_quarto.yml` | Site config (Claude builds) |
| `index.qmd` | Home page, with a listing of posts |
| `methods.qmd` | How studies are found, extracted, verified and analyzed |
| `posts/` | Lucas's posts, one per intervention or country (`.qmd`) |
| `analysis/` | Lucas's R: helper functions and meta-analysis scripts (not rendered as pages) |
| `data/snapshots/` | Dated CSV exports of verified Airtable rows |
| `data/processed/` | Cleaned data produced by Lucas's R |
| `_site/` | Rendered output (gitignored) |

Only `index.qmd`, `methods.qmd` and `posts/` are rendered (`project.render` in
`_quarto.yml`), so the brain files never become web pages. Add new top-level pages
to that list.

`execute: freeze: auto` is on: computational output is stored in `_freeze/`
(committed) and only re-run when a post's source changes.

## Commands

- Preview while writing: `quarto preview`
- Build: `quarto render`
- Publish: `quarto publish gh-pages` (renders, then pushes `_site/` to the
  `gh-pages` branch; live in a few minutes). Commit and push `main` too, including
  `_freeze/` once posts have R code. Non-interactive form:
  `quarto publish gh-pages --no-prompt --no-browser`.

## R environment

`renv` is set up by Lucas in the first R session (creates `renv.lock`). Packages:
tidyverse, metafor, fixest, sandwich, lmtest, reactable, WDI, here, renv.
