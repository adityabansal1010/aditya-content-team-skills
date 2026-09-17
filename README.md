# Team Aditya — Skills Marketplace

Private plugin marketplace carrying the house content system for Aditya Bansal's content team: voice standards, editorial judgment, LinkedIn writing frameworks, client voice profiles, and outreach playbooks.

**This repository is private and must stay private.** It contains client voice material and third-party paid content (see Licensing below).

## Install

The repo is private, so the Claude account doing the installing must be able to see it on GitHub first:

1. **Give the account's GitHub user access** — on GitHub: repo → Settings → Collaborators → add the GitHub account that team member signs into Claude with.
2. **Install the Claude GitHub App on this repo** — private marketplaces sync through the app, not through a raw clone. Personal access is verified against that user's GitHub token; the sync itself runs on the app installation token.
3. In the Claude app (web or desktop), open **Customize → Plugins → Personal plugins → `+` → Add marketplace → Add from a repository**, and enter `adityabansal1010/aditya-content-team-skills`. A git URL or `git@github.com:adityabansal1010/aditya-content-team-skills.git` also works.
4. Install the **`team-aditya`** plugin from the marketplace that appears, and enable it.

The skills then show up in the skill list — `/` or the `+` button in a chat — and load automatically when a request matches their description.

In Claude Code:

```bash
/plugin marketplace add adityabansal1010/aditya-content-team-skills
/plugin install team-aditya@team-aditya
```

**If the GitHub App route is blocked**, the fallback is Customize → Skills → Add, uploading one `.zip` per skill folder (the folder containing `SKILL.md` must be the zip's root). That works without GitHub, but it is 23 uploads and every update has to be re-uploaded by hand — the marketplace is worth the setup.

## Update

Edit a `SKILL.md` on GitHub (or push a commit), then refresh the marketplace from the plugin settings in the team account, or run `/plugin marketplace update team-aditya` in Claude Code. Updates are not automatic — someone has to pull them.

## What's inside

**Orientation**

| Skill | Purpose |
|---|---|
| `who-is-working` | **Runs first.** Establishes which team member is in the session, then adapts tone, defaults, and approval expectations. Holds the team roster. |
| `team-context` | Who the team writes for and the standards every deliverable clears. |
| `working-with-aditya` | How to talk to Aditya: verdict first, specifics, one next action. |

**Voice targets** — one of these is always loaded before drafting

| Skill | Purpose |
|---|---|
| `aditya-voice` | Writing content as Aditya. |
| `vivek-upavise` | Vivek Ravisankar (HackerRank). Voice profile, tier model, quote bank, kill filter. |
| `raag-voice` | **Scaffold only** — awaiting source material. Not ready for drafting. |
| `lgos-client-content` | Fallback voice analysis for a client with no dedicated profile. |

**Standards and judgment**

| Skill | Purpose |
|---|---|
| `signal-voice-guard` | The anti-AI floor. Runs on every output, after the voice target is set. |
| `signal-editor` | Editorial pass: scorecard, loop audit, substitution test, publish/revise/kill. |

**Craft library**

`li-writing-coach` · `storytelling-formats` · `lgos-content-writer` · `lgos-niche-finder` · `lgos-outreach` · `lgos-sales-script` · `lgos-30day-roadmap` · `linkedin-ghostwriter-os` · `brandbuilder-audience-research` · `brandbuilder-content-pillars` · `brandbuilder-positioning-consultant` · `brandbuilder-post-writer` · `brandbuilder-profile-audit`

**New business** (not client delivery)

`signal-lead-engine` · `signal-outreach-craft` · `signal-inbound-funnel`

**Commands:** `/pgali-write-post` · `/pgali-create-post` · `/pgali-hooks` · `/pgali-remix-voice`

## The rules that govern everything

**Establish the person, then work.** `who-is-working` runs at the start of a session. The account is shared, so a claimed name shapes tone and defaults but never grants authority — every deliverable needs Aditya's approval regardless of who is in the session.

**Voice target first, then the floor.** A voice skill sets what the writing should sound like; `signal-voice-guard` enforces the anti-AI floor and audits the result. Load both, in that order.

## Adding a team member

Open `plugins/team-aditya/skills/who-is-working/SKILL.md`, copy a roster block, fill in the five fields (owns / load / default mode / approves / notes), add a column to the comparison table, and commit. Nothing else needs to change.

## Configuration needed before first use

- **`signal-lead-engine`** — `references/crm-schema.md` and `SKILL.md` contain `CONFIGURE:` markers where the outreach Google Sheet and Drive folder names belong. Fill these in or the CRM protocol has nothing to point at.
- **`raag-voice`** — scaffold. See the intake list in that file for the material required.
- **`team-context`** — the Raag entry is marked `CONFIRM`. Verify before anyone drafts for him.

## Licensing

Mixed, and the reason this repo stays private:

- `signal-*`, `team-context`, `working-with-aditya`, `aditya-voice`, `raag-voice`, `vivek-upavise` — proprietary to Signal / Aditya Bansal.
- `signal-voice-guard` builds on `avoid-ai-writing` v3.16.0 by Conor Bronsdon (MIT), with supplemental tells merged from `anti-ai-slop-writing`, `llm-cliches`, and `remove-ai-tells`.
- `lgos-*` and `linkedin-ghostwriter-os` — third-party paid material (LinkedIn Ghostwriter OS).
- `brandbuilder-*` — third-party paid material (LinkedIn Brand Builder), repackaged here for internal team use only.

Third-party material is included for internal use by this team. Do not make this repository public or redistribute it.
