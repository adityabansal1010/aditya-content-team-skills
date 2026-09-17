# Loop 2 Protocol — Research, Audit, Draft

Run per prospect, in Loop 2 Priority order (🔴 High first). Budget roughly 3–5 searches per prospect; go deeper for 🔴 High.

## Step 1 — Research checklist

For each prospect, gather:
1. **Current role check** — web_search "[name] [company]" for the latest news. Catch acquisitions, departures, pivots. If role changed, mark `Disqualified` or update, note why.
2. **LinkedIn activity** — web_search "[name] LinkedIn posts [company]" / fetch their announcement posts. Determine: posting frequency, last post recency, what they post about, engagement level.
3. **Recent trigger events** — funding, product launch, podcast appearance, hiring spree, award, conference talk. The freshest specific event becomes the message hook.
4. **Their words** — a quote from an interview, podcast, or their own post. Referencing something they *said* beats referencing something about them.
5. **Company motion** — what they sell, who to, current push (new market, new product, hiring for sales = growth mode).

Output per prospect: a 5–8 line research brief.

## Step 2 — LinkedIn audit (the give-first asset)

Assess their content against these questions and write 2–3 specific, useful observations:
- Are they posting? How often? (Silent / sporadic / consistent)
- Is the content founder-voice or corporate-voice? Does it pass the substitution test (if anyone could have posted it, it's not worth posting)?
- Are they writing about what they uniquely know, or generic industry takes?
- Engagement vs. follower count — is the audience there but unactivated?
- What's the one change that would most improve results?

The audit is the free value. At least one audit observation must appear in the DM or email. It must be specific enough that only someone who actually looked could have written it.

## Step 3 — Draft the three messages

### Voice rules (all messages, non-negotiable)

- No em dashes, no emojis, no bold, no AI-sounding openers ("I hope this finds you well", "I came across your profile", "I couldn't help but notice")
- Simple vocabulary, assertive tone, mix of short and long sentences
- Lead with the specific observation or result, never with who the sender is
- Give first: every message contains something useful to them regardless of whether they reply
- Soft door, not hard pitch: end with a low-pressure line, never "can we hop on a call"
- Never fabricate familiarity ("loved your recent post" only if the post is named)

### Message 1 — Connection invite (≤300 characters, hard limit)

Structure: specific observation → one line of value or credibility → soft close. No pitch. Count characters including spaces and state the count under the draft. If over 300, cut and recount before delivering.

Example shape (287 chars):
> Saw your Series A announcement, congrats. Noticed your last 10 posts are company updates in a press-release voice. Founders in your space get 5x the reach writing in first person. I ghostwrite for SaaS founders (Peak XV, Tibo). Happy to share what's working, no pitch.

### Message 2 — LinkedIn DM (after connection accepted; 60–120 words)

Structure:
1. Proof of work: the specific audit observation (1–2 lines)
2. Value without ask: one concrete idea they could use today (a post angle, a positioning fix)
3. Soft door: "Thought you'd find this useful" / "No response needed, just wanted to share"

### Message 3 — Cold email (only if email confidence is Confirmed; 80–130 words)

- Subject: 3–6 words, specific, lowercase-casual works ("your linkedin after the raise", "one post idea for [company]")
- Same give-first structure as the DM, slightly more context on who the sender is (one line: 40+ founders, 250M+ impressions, clients like Peak XV and Tibo)
- One clear soft CTA ("worth a 15-min look sometime?" is the hardest close allowed)
- If email is Pattern-guess: still draft it, but label "SEND ONLY AFTER HUNTER.IO VERIFICATION"

### Segment-specific hooks

- **Recently Funded:** reference the raise + the 2–8 week momentum window; angle = "your announcement got X reactions, that attention decays in weeks unless you keep publishing"
- **YC Alumni:** batchmates building in public; angle = distribution as the YC-network expectation they're not meeting
- **Second-time Founder:** "you've seen what skipping distribution cost last time"
- **Solo GP:** "your LPs are on LinkedIn, your content is on Twitter"; fundraise = distribution game
- **PE-backed CEO:** new-leader credibility window; internal teams won't build his public voice
- **India D2C:** founder-brand playbook (consumer trust follows the founder); price and examples in Indian context
- **VC Partner:** deal flow follows visibility; portfolio founders amplify

## Step 4 — Delivery format

One artifact per batch containing, per prospect:

```
## P0XX — [Name], [Company] (🔴/🟡/🟢)
RESEARCH BRIEF: [5–8 lines]
AUDIT: [2–3 observations]
INVITE (XXX chars): [text]
DM: [text]
EMAIL — Subject: [text] / Body: [text]  (or "No verified email — LinkedIn only")
```

Plus at the end: a TSV block updating Pipeline Status to `Loop 2 Done` for processed IDs, and TSV rows for the Drafts tab per `crm-schema.md`.

Close with: suggested send order (warmest first, with one-line reasons), prospects to skip/postpone with reasons, and a reminder that nothing sends until Aditya approves.
