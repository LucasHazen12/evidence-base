# Schema (Airtable)

One study usually reports several results, so studies and estimates live in
separate tables joined by linked records (Airtable's version of a SQL foreign key).

**Only rows Lucas marks verified flow into the R analyses.**

Status: planned from the blueprint; the base is built in step 6. Field types and
anything marked TBD get settled then.

## Studies (one paper or report)

| Field | Type | Notes |
|---|---|---|
| Title | TBD | Primary field? TBD |
| Authors | TBD | |
| Year | TBD | |
| Link | URL | |
| Design | Single select | RCT, Quasi-experimental |
| Language | TBD | e.g. English, Spanish, Portuguese |
| Status | Single select | Inbox, Extracting, Verified, Excluded |
| Countries | Link → Countries | |
| Estimates | Link → Estimates | |
| PDF filename / location | TBD | How a study is matched to its PDF in `Papers` is TBD |
| Exclusion reason | TBD | Whether to record one is TBD |

Status flow: Inbox → Extracting → Verified, or → Excluded at any point.

## Estimates (one effect from one study)

| Field | Type | Notes |
|---|---|---|
| Outcome | TBD | Outcome naming/categories TBD |
| Effect size | Number | Metric (raw units vs standardized/SD units) **TBD** |
| Standard error | Number | Handling when only CIs, t-stats or p-values are reported: TBD |
| Sample size | Number | |
| Follow-up months | Number | |
| Page or table cited | Text | Where in the PDF the number comes from |
| Verified | Checkbox | Ticked only by Lucas |
| Study | Link → Studies | |
| Intervention | Link → Interventions | |

## Interventions (one program type, e.g. unconditional cash transfers)

| Field | Type | Notes |
|---|---|---|
| Name | Text | |
| Definition | Long text | |
| GiveWell relevance | TBD | |
| Estimates | Link → Estimates | |

## Countries (one country)

| Field | Type | Notes |
|---|---|---|
| Name | Text | Code standard (ISO3?) TBD |
| Region | TBD | Classification source TBD |
| Income group | TBD | Source TBD (World Bank?) |
| Studies | Link → Studies | |
