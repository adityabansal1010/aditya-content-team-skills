---
name: signal-lead-engine
description: The two-loop outreach system for Signal's LinkedIn ghostwriting pipeline. Use this skill whenever the writer says "Run Loop 1", "Run Loop 2", "find me leads", "find prospects", "add prospects to the pipeline", "run the outreach system", "write outreach messages", "lead generation", or mentions the CRM, pipeline, targeting brief, or cold outreach batches. Also trigger when asked to research a prospect, audit a founder's LinkedIn, or draft connection requests, DMs, or cold emails for potential ghostwriting clients. This skill contains the complete self-sufficient discovery playbook — never ask the writer to find companies or prospects themselves.
---

# Signal Lead Engine

A two-loop lead generation and outreach system for the team's LinkedIn ghostwriting agency (Signal). Aditya touches the system exactly twice: he triggers a loop, and he reviews drafts before sending. Everything in between — discovery, qualification, research, auditing, message drafting — is done autonomously using the playbooks in this skill.

**Core rule: never ask the writer to find companies, people, or contact details. The discovery playbook in `references/discovery-playbook.md` contains every source and method needed. If one source fails, use the next.**

## System overview

```
OPERATOR (trigger: "run the engine" / "run a batch")
     ↓
MERGED RUN (one segment, 5–6 prospects max):
- Read Pipeline tab → last ID + duplicate check
- Discover prospects via playbook (≤15 discovery calls)
- Qualify, verify identity + LinkedIn
- Research each + LinkedIn audit
- Draft 3 messages per prospect (invite ≤300 chars, DM, email)
- Deliver in chat: readable briefs + messages,
  then headerless TSV blocks per tab (paste-ready)
  (Drive CSV only for 8+ new-prospect batches or on request)
     ↓
OPERATOR: imports CSV, pastes TSV, sends DMs at their convenience
```

**Batch size is capped at 5–6 prospects per run, one segment per run.** This is deliberate: a merged discovery+research+drafting run for 6 prospects is ~30–40 tool calls; going to 10+ risks the run dying mid-batch with nothing shipped. Complete meals over big plates. Legacy mode: if the operator asks for "Loop 1 only" (discovery without drafts) or "Loop 2" on existing `Loop 1 Ready` rows, honor that — same protocols, just split.

## Approval gates (hard rules)

1. Never send anything. All messages are drafts; Aditya sends every DM and email himself. Never use Gmail, LinkedIn automation, or any channel to contact a prospect directly.
2. If the operator triggers a run without naming a segment, ask one short question (which segment), then run. No further approval needed mid-run — deliver the complete batch.
3. Before adding new dropdown values or columns to the CRM schema, get Aditya's explicit approval.
4. Flag any prospect with unresolved verification issues (acquisition, role change, unverified email) in the Notes column rather than silently including or excluding them.

## Loop 1 — Discovery protocol

**Hard execution budget (non-negotiable):** Max ONE fetch/search attempt per source. If a fetch returns no usable prospect data (empty page, only a title, signup wall, JS-rendered shell), that source is dead for this run — move to the next immediately, no retries, no reformulating the same URL. Max ~15 total discovery tool calls per Loop 1 run. When the budget is spent, deliver whatever qualified prospects exist — a partial batch of 4 with a note beats a full batch that never arrives. NEVER end a Loop 1 run without a TSV output, even if it contains only 2 rows.

1. Read `references/discovery-playbook.md` for the chosen segment(s). It contains sources, exact URLs, search query templates, and qualification criteria for all seven segments.
2. Find candidate companies/people using the playbook sources. Default to web_search with site: queries; use web_fetch ONLY on article-style pages (news posts, team pages), NEVER on aggregator/database homepages — those are usually JS-rendered or signup-gated and return empty shells. Work through sources in the order listed; if a source is paywalled, dead, or empty, move to the next.
3. Qualify each candidate against the segment's criteria AND the global disqualifiers (in the playbook).
4. For each qualified prospect, verify: (a) they are currently in the stated role (search "[name] [company]" for news of departures/acquisitions), (b) their LinkedIn URL resolves to the right person (construct from name, verify via search results), (c) company size and ARR/funding estimate from at least one source.
5. Research email addresses: check company website, funding announcements, podcast/newsletter pages, personal sites. Note confidence level (Confirmed / Pattern-guess / Unknown) in Notes. Never present a pattern-guess as confirmed — flag "verify via Hunter.io".
6. Output the batch as a TSV artifact following `references/crm-schema.md` exactly. Every dropdown value must match the schema's allowed values character-for-character. Include a one-line "why they're a fit" note per prospect.
7. End by summarizing: segment mix, warmest leads, any verification flags, and "Say 'Run Loop 2' when ready."

## Loop 2 — Research + Draft protocol

1. Read `references/loop2-protocol.md` in full before drafting anything. It contains the research checklist, the LinkedIn audit framework, message rules, the house voice constraints, and worked examples.
2. Ask the operator to paste (or confirm) the batch of "Loop 1 Ready" prospects, or use the batch from earlier in the conversation.
3. For each prospect, in order of Loop 2 Priority (🔴 High first): run the research checklist, produce a 5-8 line research brief, run the LinkedIn audit, then draft the three messages.
4. Deliver as one artifact per batch: research brief + audit + three message drafts per prospect, plus a TSV block of Pipeline status updates (Status → "Loop 2 Done") and Drafts-tab rows.
5. Every connection invite must be ≤300 characters including spaces. Count characters and state the count. If over, cut and recount.
6. End with a short summary: which prospects have the strongest hooks, suggested send order, and any prospects to skip or postpone with reasons.

## CRM

The CRM is the team's outreach Google Sheet (**CONFIGURE: sheet name**), which lives inside a Drive folder (**CONFIGURE: folder name**). The exact schema, column order, and allowed dropdown values live in `references/crm-schema.md`.

**Delivery method (in priority order):**
1. **If Google Drive tools are connected:** Before building a batch, read the Pipeline tab of the outreach sheet (search Drive for it by title) to confirm the last used prospect ID and check for duplicate names. Then upload the batch as a CSV file named `loop1_[segment]_[YYYY-MM-DD].csv` into the configured Drive folder. The operator imports it via File → Import → Append to current sheet. Drive tools cannot edit cells inside a native Sheet directly — never claim otherwise.
2. **If Drive is not connected:** deliver copy-paste-ready TSV in an artifact.

Never use markdown tables for data the operator needs to paste, and never output values outside the defined dropdowns.

## Segments (summary — full criteria in discovery playbook)

| # | Segment | One-line profile |
|---|---------|------------------|
| 1 | Global SaaS Founder | B2B SaaS, $5–10M ARR, 20–200 employees |
| 2 | VC Partner | Partner/GP at established fund |
| 3 | India Large-cap | Large Indian company or Tier-1 Indian VC (higher revenue bar) |
| 4 | Recently Funded | Series A/B closed 2–8 weeks ago |
| 5 | YC Alumni | 2021–2024 batch that has since raised A/B |
| 6 | Second-time Founder | Exited/experienced founder on a new venture |
| 7 | Solo GP / Emerging Manager | Raising or deploying Fund I/II |
| 8 | PE-backed CEO | New CEO installed post-acquisition |
| 9 | India D2C Founder | Indian consumer brand, post-Series A |

## Offer positioning (context for all messages)

LinkedIn authority building. No templates, fully voice-matched. Proof: 40+ clients across six countries, 250M+ impressions, clients include Peak XV Partners and Tibo (Taplio/Tweethunter). Pricing anchors: $1,500–$3,000/month global; higher revenue bar and localized pricing logic for India. Philosophy: give first — every message leads with a specific observation or piece of value, never an ask.
