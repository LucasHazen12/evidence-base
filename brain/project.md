# Project

**Evidence Base** (working name): a living, public evidence base on development
interventions. Agents find studies and draft their results; Lucas verifies them
and writes the R analyses; a Quarto website (and later a newsletter) publishes
what the evidence says.

## Mission

Make the evidence on development interventions easy to read, honest about
uncertainty, and continuously updated as new studies appear.

## Audience

A GiveWell-type reader: wants specific numbers, stated uncertainty, and no hype.

## First focus

Cash transfers, with a Latin America focus.

## Roadmap (setup checklist from the blueprint)

1. [x] Claude project "Evidence Base" with instructions, blueprint and CV
2. [x] Google Drive folder "Evidence Base" with a `Papers` subfolder, synced via Drive for desktop
3. [x] Repo folder outside Drive: `~/Projects/evidence-base`
4. [x] Tools installed (Homebrew, Git, gh, Claude Code, R + RStudio, Quarto, Drive for desktop)
5. [x] Scaffold the brain and site, create the GitHub repo, push
6. [ ] Build the Airtable base from `brain/schema.md`, create a personal access token, add the Airtable connector to `.mcp.json`
7. [ ] First real run: scout 20 studies on cash transfers in Latin America into the Inbox, then verify 5 estimates by hand
8. [ ] Once the scout works locally: connect GitHub for cloud sessions (`/web-setup`) and schedule the scout weekly (`/schedule`)

Later: newsletter (Buttondown or Substack) after 3 posts; possibly move the
data to DuckDB and query it with SQL from R once the structure is stable.

## Current phase

Setup. See `status.md` for the live state.
