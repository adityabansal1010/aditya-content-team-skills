# Discovery Playbook

Complete, self-sufficient instructions for finding prospects in every segment. Never ask the operator to supply names, companies, or lists. Work through sources top to bottom; if one is paywalled, dead, or thin, move to the next. All URLs verified as of July 2026 — if one 404s, search for its current equivalent rather than stopping.

## Fail-fast rule (applies to every source below)

One attempt per source, then move on. A fetch that returns only a page title, a signup prompt, or no prospect names is a FAILED source — do not retry it, do not fetch a different page on the same site, do not wait on it. Aggregator/database sites (Growth List, VCBacked, Fundup, Seedtable, Crunchbase, YCDB) frequently render content client-side with JavaScript, which web_fetch cannot execute: expect empty shells from them and treat search-based sources as the reliable workhorses. Track a rough call count; at ~15 discovery calls, stop searching and ship the batch with whatever qualified.

## Global disqualifiers (apply to every segment)

Exclude:
- Agencies, marketing consultancies, coaches, course-sellers (they DIY content or are competitors)
- Pre-seed / pre-revenue companies and 1–3 person teams (budget mismatch at $1,500–$3,000/month)
- Companies acquired or shut down (always verify current status)
- Founders who already work with a known ghostwriter AND post consistently in a strong voice (no gap to fill) — but a founder who *hired* a ghostwriter recently signals budget + belief; judge by whether their content still has an obvious gap
- Anyone already contacted (check Pipeline for the name before adding)

## Universal verification steps (every prospect, every segment)

1. web_search "[full name] [company]" — confirm current role, catch acquisitions/departures.
2. Confirm LinkedIn URL: search "[full name] LinkedIn [company]"; use the URL from results, don't fabricate slugs.
3. Estimate ARR/funding from: funding announcements, Latka podcast/database mentions, press interviews, job posting volume (aggressive hiring = funded/growing), G2/Capterra presence.
4. Email discovery order: (a) company site /about /contact pages, (b) personal website, (c) podcast guest pages and newsletter footers, (d) funding press releases (PR contacts sometimes include founder email), (e) common patterns (first@domain, first.last@domain) — label these "Pattern-guess, verify via Hunter.io".

---

## Segment 1: Global SaaS Founder ($5–10M ARR, 20–200 employees)

**Sources, in order:**
1. **Latka database / podcast** — web_search "site:getlatka.com [category] SaaS" or "Nathan Latka podcast [niche] founder ARR". Founders self-report ARR here; most reliable free ARR source.
2. **SaaS communities' member rosters** — web_search "SaasRise members", "Practical Founders podcast guests", "MicroConf speakers [year]". Community-active founders in the $2–15M range; each guest page gives name, company, story.
3. **G2 category pages** — web_fetch g2.com category (e.g. "sales engagement software"), look at mid-tier vendors (not leaders quadrant — those are too big). Cross-check team size on LinkedIn company page.
4. **Founderpath / Pipe / capital providers' portfolio and case studies** — web_search "Founderpath portfolio companies" — bootstrapped SaaS taking growth debt is exactly $2–10M ARR profile.
5. **Google queries:** `"$5M ARR" OR "$7M ARR" OR "hit $10M ARR" SaaS founder LinkedIn`, `bootstrapped SaaS "we reached" ARR site:linkedin.com/posts` (founders announce milestones publicly).

**Qualify:** B2B (not consumer), 20–200 employees (LinkedIn company page), founder still CEO, English-language market.

## Segment 2: VC Partner (established fund)

**Sources:**
1. Fund team pages — pick 15–20 established funds (Sequoia, Accel, Index, Bessemer, Insight, Lightspeed, a16z speedrun partners, plus vertical funds in SaaS/fintech), web_fetch their /team pages, list Partners/GPs.
2. web_search "new partner announcement venture capital [month year]" — newly promoted partners need to build a public presence fast; warmest sub-profile.
3. Podcast guest lists: "20VC guests [year]", "Invest Like the Best guests" — media-comfortable VCs value distribution.

**Qualify:** Partner/GP title (not associate/principal), fund with ≥2 vintages or ≥$100M AUM, posts occasionally but inconsistently (the gap is the pitch).

## Segment 3: India Large-cap / Tier-1 Indian VC

**Sources:**
1. Tier-1 fund team pages: Peak XV, Accel India, Elevation, Blume, Lightspeed India, Nexus, Matrix (Z47), Stellaris.
2. web_search "ET500 companies CMO CEO LinkedIn", "NSE listed company founder LinkedIn active" for large-cap leaders.
3. Inc42's lists: web_search "site:inc42.com 30 startups to watch" — monthly list of momentum companies.

**Qualify:** Higher revenue bar (₹100Cr+ revenue or Tier-1 fund) because Indian pricing is lower; decision-maker must be the person whose LinkedIn it is.

## Segment 4: Recently Funded (Series A/B, 2–8 weeks post-announcement)

The timing window matters: <2 weeks = inbox flooded with congratulations and vendor pitches; >8 weeks = momentum narrative stale. Target announcements from 2–8 weeks ago.

**Sources, in order (search-based first — these reliably return founder names, dates, and quotes in one call):**
1. **Finsmes** — web_search `site:finsmes.com "Series A" [month year] [B2B/software/industry keyword]` — highest-yield source in testing: every result names the founder/CEO, the exact date, round size, and investors. Run 2–3 variations (Series A / Series B / different industry keywords) to fill a batch.
2. **TechCrunch funding coverage** — web_search `site:techcrunch.com "raises" "Series A" [month year]`; articles name founders and quote them (quote = personalization material). Only web_fetch a specific article if the snippet lacks the founder's name.
3. **Google News queries:** `"announces Series A" OR "raises Series B" [industry]` filtered to past month; `"$10 million Series A" B2B` etc.
4. **VC firm announcement posts** — web_search "[fund name] announces investment [month year]"; funds blog about new portfolio companies with founder background included.
5. **LinkedIn announcement posts** — web_search `site:linkedin.com/posts "excited to announce" "Series A" [month year]` — the founder's own announcement post is both discovery and the perfect thing to reference in the invite.

**Fallback aggregators (⚠️ known JS-rendered/signup-gated — expect web_fetch to return empty shells; try via web_search `site:` queries instead, one attempt each, and skip on failure):**
6. **Growth List** — growthlist.co/funded-startups (confirmed empty-shell on direct fetch in testing)
7. **VCBacked** — vcbacked.co/recently-funded-companies (loads but low B2B relevance in testing)
8. **Fundup AI** — fundup.ai/recently-funded-startups
9. **Seedtable** — seedtable.com/recently-funded-startups
10. **ProjectStartups** — projectstartups.com

**Qualify:** Round is Series A or B (seed usually too small a team; C+ has comms teams), $4M–$40M raised, B2B preferred, founder-CEO still in seat, announcement date within the 2–8 week window (state the date in Notes).

## Segment 5: YC Alumni (2021–2024 batches, subsequently raised A/B)

The filter that matters: YC batch alone isn't enough — recent batches are cash-poor 2-person teams. Target companies from W21–S24 batches that have raised a Series A or B *after* YC.

**Sources:**
1. **YC official directory** — https://www.ycombinator.com/companies — filter by batch (W21, S21, W22, S22, W23, S23, W24, S24), industry (B2B), status (Active), and "Is Hiring" (hiring = budget signal). No bulk export exists; work through filtered pages via web_fetch.
2. **Cross-reference funding:** for each candidate, web_search "[company] Series A" — only keep those with a post-YC priced round.
3. **YCDB** — https://www.ycdb.co/ — sortable YC database, useful for batch-level scans.
4. **Shortcut:** web_search `"YC W22" OR "YC S22" "Series A" raised [year]` — surfaces exactly the intersection directly.
5. **YC Top Companies lists** — https://www.ycombinator.com/topcompanies — companies here are usually too big; use as an exclusion check.

**Qualify:** Post-YC A/B raised, 15–150 employees, founder-CEO active on the company (check their LinkedIn last-post date — inconsistent posting is the opening). Demo Day season (typically ~March and ~September) is a natural trigger event for adjacent batches.

## Segment 6: Second-time Founder (new venture)

**Sources:**
1. web_search `"second time founder" OR "serial entrepreneur" launches [year]`, `"sold my last company" "starting" site:linkedin.com/posts`.
2. Acquisition follow-ups: web_search "[acquired company] founder new startup" for founders whose companies were acquired 1–3 years ago.
3. Stealth-emerging: web_search `"coming out of stealth" founder previously [month year]` — press always mentions the prior company.
4. Recently funded lists (Segment 4 sources) — scan founder bios for "previously founded", "second company", "exited".

**Qualify:** Prior company had a real outcome (acquisition, $5M+ ARR, or notable scale), new venture is funded or revenue-generating, founder is the public face. Pitch angle: they know distribution compounds; they skipped it last time.

## Segment 7: Solo GP / Emerging Manager (Fund I/II)

**Sources:**
1. web_search `"closes Fund I" OR "closes Fund II" solo GP [year]`, `"emerging manager" "first fund" announcement [year]`.
2. Axios Pro Rata, Fortune Term Sheet coverage: web_search `site:axios.com "Fund I" [year]`.
3. Twitter/X-native GPs: web_search `solo GP fund launch [niche] [year]` — solo GPs announce loudly; their raise IS a distribution exercise.
4. AngelList/Wellfound rolling funds: web_search "rolling fund launch [year] [niche]".

**Qualify:** Fund I or II, $10M–$150M target, actively deploying or raising, LinkedIn presence weaker than their Twitter (the arbitrage pitch: their LPs are on LinkedIn, not Twitter).

## Segment 8: PE-backed CEO (post-acquisition)

**Sources:**
1. web_search `"appoints" CEO "portfolio company" private equity [month year]`, `"names new CEO" acquired [month year]`.
2. PE Hub / PR Newswire: web_search `site:prnewswire.com "private equity" "new CEO" [month year]`.
3. Mid-market PE firm news pages: web_fetch news/press pages of firms like Vista, Thoma Bravo (large), and mid-market firms (Mainsail, Five Elms, PSG) — mid-market is the right size.

**Qualify:** CEO installed within last 6 months, company 50–500 employees, B2B. Pitch angle: new leader needs external credibility fast, and nobody else is pitching them content.

## Segment 9: India D2C Founder (post-Series A)

**Sources:**
1. **Entrackr weekly funding roundup** — web_search `site:entrackr.com weekly funding report [month year]` — comprehensive weekly list of Indian rounds with stage breakdown.
2. **Inc42 funding coverage** — web_search `site:inc42.com [brand category] Series A raised [year]`; Inc42's D2C trackers list funded consumer brands.
3. **YourStory daily roundup** — web_search `site:yourstory.com startup news daily roundup [date]` — daily funding items with founder names.
4. Shark Tank India alumni who subsequently raised institutional rounds: web_search "Shark Tank India company Series A [year]".

**Qualify:** Series A+, ₹30Cr+ raised or ₹50Cr+ revenue, founder-led brand story (the Mamaearth/boAt founder-brand playbook), founder posts sporadically. Price in ₹ (₹40k–₹1L/month anchors), not USD.

---

## Output requirement

Every Loop 1 run ends with a TSV artifact per `references/crm-schema.md`, a summary of segment mix and warmest leads, verification flags, and the prompt "Say 'Run Loop 2' when ready." Never end a Loop 1 run by asking the operator to find or verify anything themselves — flag open items in Notes and move on.
