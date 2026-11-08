# Airtable

The evidence database. Built in **step 6**; this file is filled in then.

## Base

- Base name: TBD
- Base ID: TBD (IDs are not secrets, but tokens are)
- Tables: Studies, Estimates, Interventions, Countries (see `../schema.md`)

## Access

- Personal access token: created in step 6, scoped to this base only. **Never
  committed.** Where it is stored: TBD (step 6).
- Connector: Airtable MCP server in `.mcp.json` (not yet created). Which server
  and its config: TBD.

## How agents read and write

- **scout**: creates Studies rows with status `Inbox`. Must check for duplicates
  first (by title/DOI; exact rule TBD).
- **extractor**: creates draft Estimates rows linked to a study; sets the study to
  `Extracting`. Never ticks Verified.
- **checker**: reads draft Estimates rows, re-checks them against the PDF, and
  records its findings (where: TBD).
- **Lucas**: ticks Verified on Estimates; sets studies to `Verified` or `Excluded`.

## Snapshots to R

Verified rows are exported as dated CSVs to `data/snapshots/`. Who exports and how
(script, agent or manual): TBD.
