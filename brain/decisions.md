# Decisions

Dated log. Newest at the bottom. Each entry: what was decided and why.

## 2026-11-08

- **The brain lives in the repo** (`CLAUDE.md` + `brain/`), committed to Git.
  Why: Claude Code's auto memory is only on the Mac; cloud routines and the
  Claude project need the same source of truth.
- **CLAUDE.md stays short** and imports only `project.md` and `status.md`; other
  brain files are read on demand. Why: keeps each session's context lean.
- **Two-layer rule:** Claude Code builds and runs everything except the R; Lucas
  verifies estimates and writes the analyses. Enforced by location via
  `.claude/rules/analysis-is-lucas.md`, scoped to `analysis/` and `posts/`.
- **Repo:** `~/Projects/evidence-base`, outside Google Drive. GitHub
  `LucasHazen12/evidence-base`, public. Why outside Drive: Drive sync and Git fight
  over the same files.
- **Site:** Quarto website on GitHub Pages at
  `https://lucashazen12.github.io/evidence-base/`. Publish method still TBD.
- **Papers folder is `Papers` (capital P)**, inside the Drive "Evidence Base" folder,
  synced and available offline. The blueprint's lowercase `papers` is superseded.
- **No personal emails or real local paths in committed files.** The real Drive
  path lives in `CLAUDE.local.md` (gitignored, auto-loaded in local sessions);
  committed files use the placeholder
  `~/Library/CloudStorage/GoogleDrive-<your-google-email>/My Drive/Evidence Base/Papers`.
- **Extractor and checker run only in local sessions** (they need the synced PDFs);
  **the scout can run in cloud routines** (it only needs the web and Airtable).
- **Agents are first drafts**; the scout and extractor get tested in later sessions.
- **Deferred:** `.mcp.json` / Airtable (step 6); `renv` and R packages (Lucas, first
  R session); `newsletter.md` (after 3 posts).
- **Quarto renders only site pages** (`index.qmd`, `methods.qmd`, `posts/`) via an
  explicit `project.render` list. Why: otherwise Quarto would publish `CLAUDE.md`
  and the `brain/` files as web pages.
- **`_site/` is gitignored**: rendered output is not committed to `main`.
- **`execute: freeze: auto`** in `_quarto.yml`. Why: posts with R code re-run only
  when their source changes, so publishing doesn't need every package installed.
