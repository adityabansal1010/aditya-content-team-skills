# CRM Schema

The CRM is the team's outreach Google Sheet (**CONFIGURE: sheet name**, in the Drive folder **CONFIGURE: folder name**), with tabs: **Dashboard, Pipeline, Research, Drafts, Targeting Brief** (+ Loop Log if added). Claude cannot edit cells inside the Sheet directly. Delivery: upload an import-ready CSV to the configured Drive folder (preferred, when Drive is connected) or provide TSV in an artifact (fallback). Always read the Pipeline tab first to confirm the last used ID and check for duplicates — never assume numbering from memory.

## Non-negotiable delivery rules

1. **Default delivery is in-chat, structured in two layers:** first the readable section (per prospect: short research brief, audit observations, then each message presented cleanly with the invite character count) so the operator can read and decide on the spot; then compact headerless TSV code blocks (one per tab, matching each tab's column order) and they paste it directly into the first empty cell of the tab — Sheets auto-splits columns on tabs, no import dialog needed. Keep briefs tight; the messages appear in full in the readable layer and the TSV, nowhere else.
2. **Drive CSV uploads are the exception, not the default:** use them only for Loop-1 style discovery batches of 8+ new Pipeline rows, or when the operator explicitly asks (e.g. they're on mobile). Files are headerless, named date-first (`YYYY-MM-DD_pipeline_[segment].csv`), uploaded to the configured Drive folder. Never deliver the same rows as both chat TSV and Drive CSV in one run — pick one, it wastes usage to write content twice.
3. **File naming when Drive is used: date first** so files sort chronologically and the date is visible without opening.
2. **Dropdown values must match exactly** — character-for-character, including emoji. An invalid value breaks the sheet's data validation.
3. Use `—` (em dash character) for empty/unknown cells, not blanks, "N/A", or "TBD".
4. Dates in `YYYY-MM-DD`. Added By is the operator's name.
5. Prospect IDs continue the running sequence (P001, P002, ...). Ask the operator for the last used ID if the conversation doesn't show it; this is the one detail worth a quick question because duplicating IDs corrupts the pipeline.

## Pipeline tab — column order (exact)

```
ID	Full Name	Title / Role	Company	Segment	Geography	Company Size	Est. ARR / AUM	LinkedIn URL	Email	Twitter / X	Website	Source	Added Date	Added By	Status	Loop 2 Priority	Notes
```

## Dropdown values

**Status** (lifecycle order):
- `Loop 1 Ready`
- `Loop 2 Done`
- `Approved`
- `Sent`
- `Replied`
- `Call Booked`
- `Closed Won`
- `Closed Lost`
- `Disqualified`

**Loop 2 Priority:**
- `🔴 High`
- `🟡 Medium`
- `🟢 Low`

**Segment** (exact strings from the live sheet's dropdown, verified via screenshot 2026-07-06 — use these character-for-character, never invent new ones):
- `Global Founder`
- `SaaS Founder`
- `VC Partner (Global)`
- `Indian Tier-1 VC`
- `Indian Large Co.`
- `Recently Funded`
- `YC Alumni`
- `Second-time Founder`
- `Solo GP`
- `PE-backed CEO`
- `India D2C`

**Source** (free text but prefer): `Manual`, `Growth List`, `VCBacked`, `Fundup`, `Seedtable`, `TechCrunch`, `Finsmes`, `YC Directory`, `Entrackr`, `Inc42`, `YourStory`, `Latka`, `Fund Site`, `LinkedIn`, `Google News`, `Referral`

## Notes column format

One or two sentences: why they're a fit + any verification flag. Examples of good notes:
- "Recently hired a ghostwriter. Posts heavily on LinkedIn. CEO mastermind for $1M–$100M SaaS founders. Warmest lead."
- "Raised $12M Series A on 2026-06-10 (led by Accel). Announcement post got 400+ reactions. Window closes ~2026-08-05."
- "Company acquired by Daxko — verify role before outreach."

## Email confidence labels (in Notes)

- `Email confirmed ([source])` — found on an official/public page
- `Email pattern-guess — verify via Hunter.io` — constructed from a pattern
- Leave Email cell as `—` if nothing found; LinkedIn is the primary channel anyway

## Research tab — column order (exact, verified against the live sheet 2026-07-06)

```
ID	Name	Company	LinkedIn Summary	Recent News / Activity	Key Hook / Angle	Pain Point Identified	Best Channel	Research Date	Researched By
```

Best Channel values: `LinkedIn DM`, `Email`, `Both`. Researched By is `Claude`.

## Drafts tab — column order (exact, verified against the live sheet 2026-07-06)

```
ID	Name	Company	LinkedIn URL	Connection Request	LinkedIn DM	Cold Email Subject	Cold Email Body	Gmail Draft Saved?	Operator Rating	Action Taken	Send Date	Outcome
```

Claude fills the first eight columns; `Gmail Draft Saved?`, `Operator Rating`, `Action Taken`, `Send Date`, and `Outcome` are the operator's tracking columns — leave as `—`. Connection Request must be ≤300 characters.

## Loop 2 delivery

Loop 2 output = two CSVs uploaded to the configured Drive folder: `loop2_research_[YYYY-MM-DD].csv` (Research tab rows) and `loop2_drafts_[YYYY-MM-DD].csv` (Drafts tab rows), plus the full readable briefs in the chat response. Also remind the operator to update Pipeline Status for processed IDs to the sheet's drafted status.

## Dashboard note

The Dashboard's segment breakdown uses the original four segment labels; when new segments (Recently Funded, YC Alumni, etc.) start flowing, remind the operator once to add rows for them in the Dashboard breakdown and to extend the Pipeline Segment dropdown validation.
