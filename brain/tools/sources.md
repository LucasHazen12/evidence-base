# Sources

Where studies come from. The scout searches the evidence repositories; Lucas reads
the Latin America and benchmark sources directly.

## Scout agent

| Source | What you get |
|---|---|
| 3ie Development Evidence Portal | Impact evaluations and systematic reviews, searchable by intervention and country |
| J-PAL evaluations | RCT summaries with links to the papers |
| Innovations for Poverty Action | RCT summaries and papers |
| NBER | Recent development economics working papers |
| AEA RCT Registry | Registered trials, including unpublished ones |
| **OpenAlex** | Free API over scholarly papers (search, abstracts, citations): **the scout's main search engine** |
| IDB publications | Latin America evaluations, many in Spanish and Portuguese (scout **and** Lucas) |

## Lucas (manual)

| Source | What you get |
|---|---|
| Campbell Collaboration | Systematic reviews to check coverage against |
| IDB publications | (see above) |
| IPEA | Brazilian policy research and evaluations, in Portuguese |
| INEGI | Mexico's program evaluations; holds CONEVAL's archive since CONEVAL was dissolved in 2025 |
| GiveWell | Intervention reports and cost-effectiveness models: the benchmark |
| VoxDev | Literature summaries to orient each new topic |

## R analyses

- World Bank WDI (the `WDI` R package): country context data for posts.

## Search strategy

- First topic: cash transfers (conditional and unconditional), Latin America.
- First run (step 7): 20 studies into the Inbox.
- Cadence: weekly once scheduled as a cloud routine (step 8).
- Search terms / queries (English, Spanish, Portuguese): **TBD**
- Inclusion criteria (designs, years, outcomes, minimum quality): **TBD**
- Deduplication rule (DOI, title match): **TBD**
