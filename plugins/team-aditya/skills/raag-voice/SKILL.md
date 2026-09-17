---
name: raag-voice
description: Voice and content system for the client Raag — LinkedIn and X posts, scripts, and newsletter content written under his name. Use this skill whenever a task involves writing, drafting, reviewing, or planning content for Raag. IMPORTANT — this skill is currently a SCAFFOLD: the voice profile and quote bank have not been built yet, so it cannot yet produce a voice-matched draft. Read the intake section and ask for the missing material before drafting anything for him.
---

# Raag — Founder Voice & Content System

> ## ⚠️ SCAFFOLD — NOT READY FOR DRAFTING
>
> This file has the right shape but not the content. The voice profile, quote bank, and pillar structure are empty because the source material has not been supplied yet.
>
> **Do not draft content for Raag from this file in its current state.** Writing in an undocumented voice and calling it his is exactly what the house standards forbid — voice is a claim you back with evidence, and there is no evidence here yet.
>
> If asked to write for Raag now: say the voice system isn't built, ask for the material listed below, and offer to run the voice analysis as soon as it arrives. If a draft is genuinely urgent, use `lgos-client-content` to analyse whatever samples are available in the moment and state plainly in the output that the draft is un-calibrated and needs Aditya's review before it goes anywhere near the client.

## What this skill needs before it works

Gather these, then build out the sections below. The Vivek instance (`vivek-upavise`) is the reference standard for what "finished" looks like: a 60-line voice profile plus a 400-line quote bank organised by content pillar.

**1. Writing samples — the minimum viable input.**
15–30 of Raag's posts, ideally ones he wrote himself or approved without edits. Published posts are fine; approved drafts are better, because they show what he accepts rather than what he tolerated. From these, extract sentence-length pattern, contraction rate, paragraph openings, recurring word choices, and register. Do not upgrade his vocabulary: if he writes plainly, keep it plain.

**2. Transcripts — what makes the quote bank possible.**
Podcast appearances, interviews, internal calls, voice notes, anything where he talks at length. This is where his actual phrasing, analogies, and stories live. The Vivek quote bank works because it is built from transcripts, not from posts. Without transcripts you get a style match with nothing true to say.

**3. The brief.**
- What he is positioning for, and who he is talking to
- Which platforms, and the cadence on each
- Deliverable types (posts, threads, scripts, newsletter)
- Subject matter he owns, and subject matter he will not touch
- Whether anything is under NDA or otherwise off-limits

**4. Rejections.**
Anything he has turned down or rewritten, and why. This is the highest-signal material for a kill filter and it is usually the hardest to get, so ask specifically.

## Sections to build (mirroring the Vivek instance)

Once the material above exists, fill these in. Keep the structure — it is what makes the system usable by anyone on the team rather than only by whoever did the analysis.

### Voice profile → `references/raag-voice-profile.md`
- Who he is, as context for tone
- Voice mix across the five archetypes (see `lgos-client-content`)
- Verbal habits to replicate
- Analogy library, drawn from his own usage — never imported from elsewhere
- People and sources he cites
- Content pillars
- Verified numbers bank
- Source integrity map (which claims trace to which source)
- Kill filter: the specific lines that get deleted on sight
- Sensitive handling notes

### Quote bank → `references/raag-quote-bank.md`
Organised by pillar, each with principles, stories, and spiky POVs, every entry traceable to a named source. Plus a repetition map: the things he returns to unprompted, which are his real convictions as opposed to his stated ones.

### Tier model and drafting workflow
Whether his content splits into tiers the way Vivek's does (reach vs. resonance), and the step-by-step drafting workflow with the tier assignment and sourcing check.

### Format playbooks
Per-platform specs: LinkedIn post, X, video script, newsletter — length, structure, and what changes between them.

## Rules that already apply

These hold from day one, before the profile is built:

1. **Nothing invented.** No stories, numbers, claims, or experiences fabricated for Raag. Every specific traces to the quote bank or to material he supplied.
2. **House hard-bans in force.** No em dashes or en dashes, no emojis, no bold in the body, no AI openers.
3. **Substitution test.** If the post could have been published by any other founder in his space, it has failed.
4. **Voice claims need evidence.** Point to a post, a transcript line, or a documented profile. "It sounds like him" is not evidence.
5. **Aditya approves everything** before it reaches the client.

## Pairing

`signal-voice-guard` enforces the floor on every output. `signal-editor` runs the judgment pass on a finished draft. Until this profile is built, `lgos-client-content` is the fallback for voice analysis from raw samples.
