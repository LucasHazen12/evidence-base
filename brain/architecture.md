# Architecture

How the parts connect, in words. Ten parts; two belong to Lucas (marked **[Lucas]**).

## The pipeline

1. **Evidence sources** (3ie, J-PAL, IPA, NBER, AEA RCT Registry, OpenAlex, IDB…;
   see `tools/sources.md`) →
2. **Scout agent** (`.claude/agents/scout.md`) finds new studies weekly and adds
   them to →
3. **Airtable: Studies**, an inbox of candidate studies, each tagged by status
   (Inbox, Extracting, Verified, Excluded).
4. **Google Drive: papers.** Lucas saves a PDF for every study to the Drive
   `Papers` folder, synced to the Mac.
5. **Extractor + checker** (`.claude/agents/extractor.md`, `checker.md`): the
   extractor drafts each estimate from the PDF following the `extract-estimates`
   skill; the checker re-checks every draft against the PDF. Drafts go to →
6. **Airtable: Estimates** **[Lucas]**: Lucas verifies every row and ticks
   "verified" before it is used.
7. **R analysis** **[Lucas]**: Lucas writes it in RStudio (meta-analyses with
   `metafor`), in `analysis/` and `posts/`. Only verified rows flow in, via dated
   CSV snapshots in `data/snapshots/`.
8. **GitHub repo**: the brain and all the code. Claude Code builds here.
9. **Website + newsletter**: the Quarto site on GitHub Pages; each post later also
   goes out by email.
10. **Claude project**: planning, writing and R tutoring; reads the same brain from
    the repo.

## Where each agent can run

| Agent | Local session | Cloud routine | Why |
|---|---|---|---|
| scout | yes | **yes** | Needs only the web and Airtable |
| extractor | **yes** | **no** | Needs the local PDFs in the synced Drive `Papers` folder |
| checker | **yes** | **no** | Same: re-reads the local PDFs |
| r-tutor | yes | n/a | Reviews Lucas's R on request |

**Extraction needs the local PDFs, so the extractor and checker run only in local
sessions.** The scout can run as a weekly cloud routine while the laptop is closed.

## Papers location

Committed placeholder:

    ~/Library/CloudStorage/GoogleDrive-<your-google-email>/My Drive/Evidence Base/Papers

The real path is in `CLAUDE.local.md` (gitignored, auto-loaded in local sessions,
absent in cloud sessions). The folder is set to "available offline" in Drive for
desktop so agents can read the files.

PDF file naming convention: **TBD**.

## Rules of the road

- The repo stays outside Google Drive (Drive sync and Git conflict).
- PDFs are never committed (`*.pdf` is gitignored), for copyright and size reasons.
- Secrets (Airtable token) never committed; how they're stored is decided in step 6.
- The brain is the source of truth for every session, local or cloud.

## Possible later

Move the database into DuckDB and query it with SQL from R once the structure is
stable.
