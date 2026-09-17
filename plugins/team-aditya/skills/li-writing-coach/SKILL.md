---
name: li-writing-coach
description: >
  This skill should be used when the user asks for help writing LinkedIn content,
  wants a LinkedIn writing coach, asks "how do I write a good hook", "coach me
  through writing a post", "teach me the writing system", "help me understand the
  frameworks", "what makes a good LinkedIn post", "how do I write for my client",
  or any conversational request about LinkedIn writing strategy, post structure,
  hook formats, voice matching, or content creation methodology. Also use when
  someone is stuck on what to write or wants to understand the system before
  using a command.
---

# LinkedIn Writing Coach

A complete LinkedIn writing system for ghostwriters — generate hooks, write posts, and remix voice using a proven methodology built around 11 hook formats, 5 content styles, and 5 voice archetypes.

## File Structure

```
li-writing-coach/
├── SKILL.md                        ← You are here
├── references/
│   ├── hook-formats.md             ← All 11 hook formats with examples
│   ├── post-formats.md             ← 5 content styles + 5 formatting rules + character limits
│   └── voice-archetypes.md        ← 5 voice archetypes + output table format
└── commands/
    ├── pgali-hooks.md              ← Step-by-step instructions for /pgali-hooks
    ├── pgali-write-post.md         ← Step-by-step instructions for /pgali-write-post
    ├── pgali-create-post.md        ← Step-by-step instructions for /pgali-create-post
    └── pgali-remix-voice.md        ← Step-by-step instructions for /pgali-remix-voice
```

---

## The Three-Part System

### 1. Hook Generation (11 Formats)
Every LinkedIn post starts with a hook — the first 1–3 lines visible before the "See More" button. A great hook creates an open loop that compels readers to click through. The system includes 11 distinct hook formats, each engineered for a different psychological trigger (curiosity, social proof, FOMO, belief transformation, etc.).

Full format specs and examples → `references/hook-formats.md`

Use the `/pgali-hooks` command to generate all 11 hooks for any topic.

### 2. Post Writing (5 Styles + 5 Formatting Rules)
Once a hook is chosen, the post body follows a specific structure designed for LinkedIn's 3,000-character limit. There are 5 content styles (Steps, Stats, Mistakes, Lessons, Examples) and 5 universal formatting rules that apply regardless of style.

Full style specs and formatting rules → `references/post-formats.md`

Use the `/pgali-write-post` command to generate post ideas and write the best one. Use `/pgali-create-post` for the full end-to-end flow (hooks → pick one → write post).

### 3. Voice Remixing (5 Archetypes)
When writing for clients, voice matching is essential. The Voice Remixer rewrites any piece of text in 5 archetypes — The Storyteller, The Opinionator, The Fact Presenter, The Frameworker, and The F-Bomber — so ghostwriters can identify and replicate a client's natural voice.

Full archetype specs → `references/voice-archetypes.md`

Use the `/pgali-remix-voice` command to rewrite any text in all 5 voices.

---

## Command Execution

When a user invokes one of the following commands, read the corresponding file from `commands/` and follow its instructions exactly:

| Command | Instruction file | What it does |
|---------|-----------------|--------------|
| `/pgali-hooks` | `commands/pgali-hooks.md` | Gather topic/audience/achievements → generate all 11 hooks |
| `/pgali-write-post` | `commands/pgali-write-post.md` | Generate 15 post ideas across 5 styles → write the best one |
| `/pgali-create-post` | `commands/pgali-create-post.md` | Full guided flow: hooks → pick one → complete post |
| `/pgali-remix-voice` | `commands/pgali-remix-voice.md` | Rewrite any text in all 5 voice archetypes as a table |

---

## How to Coach Conversationally

When a user asks a question about the methodology rather than requesting a command output:

1. Diagnose what they're trying to accomplish (writing for themselves vs. a client, stuck on hooks vs. post body, etc.)
2. Explain the relevant framework in plain language — read `references/hook-formats.md`, `references/post-formats.md`, or `references/voice-archetypes.md` as needed
3. Recommend the right command to execute it
4. If they're writing for a client, always suggest `/pgali-remix-voice` first to establish voice before writing content

---

## Recommended Workflows

**Writing for yourself:**
1. `/pgali-create-post` — Enter topic, audience, and achievements
2. Pick your favorite hook from the 11 options
3. Get a complete, ready-to-publish LinkedIn post

**Writing for a client:**
1. `/pgali-remix-voice` — Paste a sample of the client's existing writing
2. Identify their dominant 1–2 voice archetypes from the output table
3. `/pgali-create-post` — Write the post, then ask to rewrite it in the client's dominant archetype

**Just need hooks fast:**
- `/pgali-hooks` — Quick hook generation without writing the full post

**Already have a hook, need the post body:**
- `/pgali-write-post` — Paste your hook as the starting point and get the full post

---

## Quick Reference: Which Command to Use

| Goal | Command |
|------|---------|
| Generate hook options for a topic | `/pgali-hooks` |
| Write a complete LinkedIn post | `/pgali-write-post` |
| Rewrite text in 5 different voices | `/pgali-remix-voice` |
| Full guided flow: hook → post | `/pgali-create-post` |
| Coaching or methodology questions | Just ask — this skill handles it |
