# Evidence Base

I'm Lucas: an analyst at an economic consulting firm (damages modeling) with a
master's in international economics, building toward a research role in
development economics / effective altruism (GiveWell is the target). I work on
this project a couple of hours a week, so keep plans small and shippable.

## The two-layer rule

- **Claude Code builds and runs everything except the R**: the site, the brain,
  the agents, the Airtable plumbing, publishing.
- **Lucas verifies estimates and writes the R.** In `analysis/` and `posts/`,
  Claude reviews and gives hints only — no analysis code
  (see `.claude/rules/analysis-is-lucas.md`).
- Only estimates Lucas has marked verified flow into the R analyses.

## Always loaded

@brain/project.md
@brain/status.md

## Read only when the task needs it

- `brain/decisions.md` — dated log of decisions and why
- `brain/architecture.md` — how the tools connect; what runs locally vs in the cloud
- `brain/schema.md` — Airtable tables, fields, status values
- `brain/style.md` — voice for posts
- `brain/tools/` — airtable, sources, github, quarto

Machine-specific paths (e.g. the local papers folder) live in `CLAUDE.local.md`,
which is gitignored and exists only on Lucas's Mac.

## Before ending any session

1. Update `brain/status.md`: where things stand and the next step.
2. Append any new decisions to `brain/decisions.md` (dated, with the why).
3. Never commit personal emails, tokens or real local paths; use placeholders.
