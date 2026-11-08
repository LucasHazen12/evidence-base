# Status

_Last updated: 2026-11-08_

**Step 5 done. Next: step 6, Airtable.**

## Where things stand

- Brain (`CLAUDE.md`, `brain/`, `brain/tools/`) scaffolded from the blueprint;
  open questions marked TBD.
- Agents (scout, extractor, checker, r-tutor), the `extract-estimates` skill and
  the `analysis-is-lucas` rule exist as **first drafts**. Scout and extractor are
  untested.
- Quarto website skeleton renders locally (`quarto render`).
- Repo pushed to GitHub (public). GitHub Pages not yet enabled.

## Deliberately not done yet

- `.mcp.json` / Airtable connector: step 6.
- `renv` and R packages: Lucas does this in the first R session (creates `renv.lock`).
- `brain/tools/newsletter.md`: after 3 posts.
- GitHub Pages publishing: pending Lucas's go-ahead.

## Next step (step 6)

1. Build the Airtable base from `brain/schema.md`; settle the TBD field types.
2. Create a personal access token (scoped to that base).
3. Have Claude Code add the Airtable connector to `.mcp.json`, with the token kept
   out of Git.
4. Fill in `brain/tools/airtable.md`.
