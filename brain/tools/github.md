# GitHub

- **User:** LucasHazen12
- **Repo:** `LucasHazen12/evidence-base`, **public**
- **Local clone:** `~/Projects/evidence-base` (outside Google Drive)
- **Default branch:** `main`
- **CLI:** `gh` (logged in) lets Claude Code create the repo, push and manage settings.

## Publishing

- **Site URL:** https://lucashazen12.github.io/evidence-base/
- **Pages method:** TBD (options: `quarto publish gh-pages`, which puts the rendered
  site on a `gh-pages` branch; or a GitHub Actions workflow that renders on push).
  Ask Lucas before enabling Pages.

## Conventions

- Branch strategy: TBD (for now, commit to `main`).
- Never commit: PDFs, `.env`, tokens, `secrets/`, `CLAUDE.local.md`, renv library,
  `_site/` (see `.gitignore`).
- Before committing anything that touches paths or config, check that no personal
  email or real local path slipped in (e.g. `git grep -n "<email domain>"`).
- Cloud sessions: connect GitHub via `/web-setup` (step 8).
