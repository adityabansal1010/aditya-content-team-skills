---
name: aditya-voice
description: The voice target for writing content as Aditya Bansal — his own LinkedIn posts, X posts, newsletter issues, and long-form pieces. Use this whenever a draft is going out under Aditya's name rather than a client's, and pair it with `signal-voice-guard`, which enforces the anti-AI floor on the result. This sets the writing target; it is not the skill for how to talk to him in conversation, which is `working-with-aditya`.
---

# Aditya Voice

The target when Aditya is the client. He is one account among several the team writes for, and his own content gets the same discipline as any paying client's: voice target set here, floor enforced by `signal-voice-guard`, judgment applied by `signal-editor`.

## Target spec

- **Length:** 150–200 words for a standard LinkedIn post. Longer only when the material genuinely earns it.
- **Reading level:** Grade 6–7 vocabulary. Plain words beat impressive ones. If a shorter word works, it wins.
- **Form:** Prose, not bullets. Short paragraphs, often one or two sentences. Mix sentence lengths — a run of uniform sentences reads as machine-written.
- **Register:** Direct, a little assertive, zero corporate padding. Confident without announcing the confidence.
- **Context profile:** `linkedin`. **Voice profile:** closest to `professional` with a `blunt` lean.

## Structure

The default arc, in this order:

1. **Result or insight first.** Open on the thing that happened or the thing that's true. No windup, no scene-setting, no rhetorical question as a warm-up.
2. **Examples.** The specifics that make it credible — a number, a name, a moment, what actually happened.
3. **Principle.** What the examples add up to, stated once, plainly.
4. **Action.** What the reader should do or reconsider.

He should almost never open with a tease. His strongest posts open on the result, and the curiosity loop is "how?", which the examples then pay off. Teasing a payoff he's about to give anyway wastes the first line, which is the only line most readers see.

## Hard bans

In force at full strength, no exceptions:

- No em dashes or en dashes. Use a period, a comma, or a colon.
- No emojis anywhere, including end of line.
- No bold in the body.
- No AI openers ("Great question", "I hope this finds you well", "I came across your profile").
- No hashtag stuffing.
- No generic closers, no "what do you think?" social-endorsement sign-offs, no future-narrative wrap-ups.

## Substance rules

**Specificity is the whole product.** Run the substitution test on every draft: could any other ghostwriter or founder have published this exact post? If yes, it's dead. Real numbers, real client situations, real mistakes, real mechanics.

**Nothing invented.** No fabricated results, clients, numbers, or anecdotes, including plausible-sounding ones. If a post needs a specific he hasn't supplied, ask him for it rather than filling the gap.

**Experience is the credibility, not the credentials.** Draw on what actually happened in the work — a client outcome, a pricing decision, an editorial call, something that broke. He has the track record; posts that gesture at it vaguely are weaker than posts that show one concrete piece of it.

**No self-congratulation.** Proof points belong in a post when they carry an argument, not as a flex. The numbers do the work; the tone stays matter-of-fact.

## Pairing

Set the target here, then run `signal-voice-guard` to enforce the floor and audit the output. For a finished draft, run `signal-editor` with this skill loaded as the voice reference — the scorecard's Voice match line is scored against this spec.
