---
name: brandbuilder-profile-audit
description: >
  Audits a LinkedIn profile against a 9-point personal branding checklist (positioning statement,
  category name, headline, about section, banner, headshot, Creator Mode, skills, featured section)
  and reports findings in chat. Use this skill whenever the user wants to "audit my LinkedIn profile,"
  "review my LinkedIn," "check my client's LinkedIn profile," "grade this LinkedIn profile," "what's
  wrong with this LinkedIn page," or pastes/names a LinkedIn profile URL and wants feedback on their
  personal brand setup. Also trigger on "LinkedIn profile review," "LinkedIn checklist," or "personal
  branding audit." This skill is READ-ONLY — it browses and reports, and never edits, messages, or
  changes anything on LinkedIn or anywhere else.
---

# LinkedIn Profile Audit

Audit a LinkedIn profile against Cole's 9-point personal branding checklist using the Claude in
Chrome browser tools, and report the findings directly in chat.

## Critical rule: read-only, always

This skill is strictly an **audit** tool. Never edit, click into edit mode, change settings, post,
message, connect, follow, like, comment, or modify anything on the profile or anywhere else in the
browser. Only navigate and read. If asked to also "fix" or "update" the profile, explain that this
skill only audits — the person should make any changes themselves (or ask for the Positioning
Consultant skill to draft new headline/about copy they can paste in manually).

All output goes in the chat window as a written report. Do not create files unless the user
explicitly asks for the audit to be saved as a document.

## Step 1: Determine whose profile this is

Ask first (in one question): is this audit for the ghostwriter's own LinkedIn profile, or for a
client's profile?

- **Own profile**: proceed straight to the audit once you have the profile URL.
- **Client's profile**: also ask for the client's name/business context if not already provided —
  this helps you judge whether the positioning statement, category name, and headline actually fit
  who the client serves and what they're known for. You're auditing the same way either way; the
  only difference is whose context you're checking the content against.

If you don't have the LinkedIn profile URL yet, ask for it.

## Step 2: Navigate and read the profile

Use the Claude in Chrome tools (`mcp__Claude_in_Chrome__navigate`, `mcp__Claude_in_Chrome__get_page_text`,
`mcp__Claude_in_Chrome__find`, `mcp__Claude_in_Chrome__computer` for screenshots/zoom) to:

1. Navigate to the profile URL.
2. Read the visible profile content: name, headline, banner image, profile photo, About section,
   Featured section, Skills section, and any visible indication of Creator Mode (a "Creator Mode"
   label or topic tags under the headline).
3. Take a screenshot or zoom in on the banner and profile photo to assess them visually — you need
   to see these to judge the Headshot and Banner checklist items.
4. Scroll as needed to load and read the Skills and Featured sections (LinkedIn often lazy-loads
   these — scroll down and re-read).

If any section isn't visible or accessible (e.g., Skills section requires clicking "Show all" which
would count as an interaction beyond simple navigation — clicking to *expand/reveal* content is fine
since it's not editing anything), use `find` and `computer` to click only on reveal/expand/"show
more" controls. Never click anything that opens an editor, settings menu, or compose box.

## Step 3: Audit against the 9-point checklist

Evaluate each point. For each, give a clear verdict — **Pass**, **Needs work**, or **Missing** — plus
a one- or two-sentence note on what you observed and why it does or doesn't meet the bar.

1. **1-line positioning statement** — Is there a clear "I help [audience] solve [problem] so they
   can [result]" statement somewhere on the profile (About section opening, headline, or banner)?
   Note: LinkedIn has no dedicated field for this — check whether the *substance* of it comes through.
2. **Category name** — Does the profile use a short, specific, memorable category/role name (e.g.,
   "Onboarding Email Surgeon") rather than a generic title (e.g., "Email Marketer")?
3. **Headline** — Does it include audience + mechanism + result, and does it make good use of the
   character limit (roughly 220 characters) without being cut off or wasted on a generic job title?
4. **About section** — Is it roughly 300 words, and does it cover: who they help, the painful problem
   in the audience's own words, their method explained in plain English, proof points (metrics,
   logos, outcomes), and a clear call to action?
5. **Banner** — Does the banner image communicate a big promise (~10 words), include one proof
   metric, and carry a soft call to action? Assess this visually via screenshot/zoom.
6. **Headshot** — Is the profile photo recent-looking, on a neutral background, with the face filling
   roughly 60-70% of the frame, natural lighting, and direct eye contact? Assess this visually.
7. **Creator Mode** — Is Creator Mode turned on, and are roughly 5 relevant topics selected/displayed?
8. **Skills** — Are there roughly 20-25 skills listed, and (as best as can be observed) do they span
   four buckets — Core Expertise, Adjacent Skills, Industry Keywords, Outcome Skills — with the top 5
   ordered to match the headline?
9. **Featured section** — Are there 3 items, ideally: a lead magnet, the strongest case study, and a
   "start here" post?

## Step 4: Report the findings

Present the audit in chat as a clear written report (use light formatting — a short summary plus the
9 checklist items each with verdict + note). Close with:

- An overall snapshot: how many of the 9 points pass, need work, or are missing.
- The 2-3 highest-leverage fixes to prioritize first (the gaps most likely to hurt how the profile
  converts or positions the person).

Do not draft replacement copy unless asked — if the user wants a new headline or About section
written, point them to the Positioning Consultant skill in this plugin.

## Reminders

- Never enter edit mode, change settings, or interact with anything beyond reading/expanding content.
- Never message, connect with, follow, or otherwise act on the profile owner or anyone else.
- If the profile is private/restricted and you can't see enough to audit it, say so plainly rather
  than guessing.
