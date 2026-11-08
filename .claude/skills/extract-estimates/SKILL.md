---
name: extract-estimates
description: Step-by-step procedure for drafting Estimates rows from one study's PDF. Use when extracting results from a study for Evidence Base. Local sessions only (needs the synced PDFs).
---

<!-- FIRST DRAFT. Steps marked TBD depend on schema decisions in step 6. -->

# Extract estimates from one study

## 0. Preconditions

- You are in a **local session**: `CLAUDE.local.md` exists at the repo root and gives
  `PAPERS_DIR`. If not, stop and say extraction must run on Lucas's Mac.
- The study exists in Airtable Studies (status `Inbox` or `Extracting`).
- Its PDF is in `PAPERS_DIR`. How a study is matched to its PDF filename is
  **TBD**; for now, match by first author, year and title words, and confirm the
  match by checking the PDF's title page.

## 1. Orient

1. Read the abstract, the intro's summary of results, and the design section.
2. Note: country or countries, design (RCT / quasi-experimental), intervention
   arm(s), comparison group, sample, follow-up timing(s), and which specification
   the authors call their main one.
3. If this study is not an impact evaluation of the intervention, stop and suggest
   status `Excluded` with a reason (Lucas decides).

## 2. Find the results

1. List the main results tables and figures.
2. For each outcome relevant to the intervention, take the authors' main
   specification. Record other specifications only if the authors emphasize them.
3. Which outcomes to extract (all, or a fixed list per intervention): **TBD**.

## 3. Draft one row per effect

For each effect, fill in these fields (see `brain/schema.md`):

| Field | How |
|---|---|
| Outcome | The authors' outcome name, plus units |
| Effect size | As reported. Standardization rule **TBD**; until then, record the raw coefficient and its units |
| Standard error | As reported. If only a CI, t-stat or p-value is given, record what's given and flag it (conversion rule TBD) |
| Sample size | N for that regression |
| Follow-up months | Months from treatment start to measurement |
| Page or table cited | e.g. "p. 14, Table 3, col. 2" |
| Study / Intervention | Links |
| Verified | **Leave unticked** |

## 4. Flag

Add a flag note to any row with: unclear units, a non-main specification,
subgroup-only results, clustering not reported, conflicting numbers between
text and table, or a value derived rather than read directly.

## 5. Hand off

1. Pass all draft rows to the **checker** agent.
2. Until the Airtable connector exists (step 6), return the rows as a table in
   your final message. Afterwards: write the drafts to Estimates and set the
   study status to `Extracting` (details in `brain/tools/airtable.md`).
3. Report: rows drafted, rows flagged, and anything the checker changed.
