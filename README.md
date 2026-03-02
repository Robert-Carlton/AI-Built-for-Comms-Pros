# PR Pitching Plugin for Claude Cowork

![The AI Built for Comms Pros](./AIBuiltForCommsProsImage.jpg)

> **The AI Built for Comms Pros** — 25+ years of strategic communications expertise encoded into a zero-dependency Claude Cowork plugin. End-to-end press release pitching workflows, from news value assessment to coverage report.

[![License](https://img.shields.io/badge/license-Proprietary-red.svg)](#license)
[![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)](#)
[![Platform](https://img.shields.io/badge/platform-Claude%20Cowork-orange.svg)](#installation)

---

## What This Is

A complete PR pitching specialist that runs entirely within Claude Cowork — no Python environment, no API keys, no local dependencies. Install once, customize with your org's details, and every press release campaign runs through a structured, professional workflow.

The plugin encodes hard-won expertise across the full PR campaign lifecycle: how to assess whether a story is actually newsworthy, how to position against competitive announcements, how to build a media list that prioritizes quality over volume, how to write pitches that journalists actually read, and how to report results in a way that makes sense to leadership.

---

## Installation

1. Download or clone this repository
2. Open Claude Desktop and switch to the **Cowork** tab
3. Click **Customize** in the left sidebar
4. Click **Browse Plugins** → **Upload Custom Plugin**
5. Point it at the `pr-pitching` folder

Once installed, skills activate automatically based on context. Slash commands are available by typing `/` in the Cowork input.

---

## Quick Start

**Step 1 — Customize your org context**
Open `skills/pr-org-context/SKILL.md` and fill in your organization's boilerplate, spokespeople, key messages, media contacts, and brand voice. This is the most important step.

**Step 2 — Load your writing style**
Run `/pr-pitching:learn-style` and upload 5–10 historical press releases in any format (Word, PDF, plain text). Claude extracts your style across 13 dimensions and generates both a style guide and a fill-in-the-blanks template. No file prep required.

**Step 3 — Run your first campaign**
```
/pr-pitching:assess-news-value
```
Paste your announcement. Get an honest assessment against 14 newsworthiness criteria before writing a word.

---

## Commands

### `/pr-pitching:assess-news-value`
**Evaluates your announcement against 14 professional newsworthiness criteria before you commit to a campaign.**

Scores each dimension as High / Medium / Low with rationale, produces an overall Strong / Moderate / Weak rating, identifies your strongest angle, and flags anything that could undercut coverage. The 14 criteria cover Timeliness, Magnitude, Novelty, Proximity, Human Interest, Conflict, Prominence, Currency, Consequence, Actionability, Visual Potential, Exclusivity, Audience Relevance, and Source Credibility. If news value is weak, the plugin tells you what would strengthen it before you invest in writing or outreach.

---

### `/pr-pitching:competitive-scan`
**Research comparable announcements, identify your unique position, and sharpen your angle before drafting.**

Scans the competitive landscape for similar announcements, identifies what has and hasn't been covered in your space, surfaces defensible differentiators, and produces a positioning brief. Prevents you from pitching a story that's already been told — or missing the angle that makes yours different.

---

### `/pr-pitching:review-release`
**Audit or draft a press release against structural standards and key messages.**

Applies a 9-element structural checklist, verifies key message integration, flags red flags (unverified superlatives, buried lead, missing data attribution, passive voice overuse), and produces a scored assessment with specific revision recommendations. Can also draft from scratch using your org's extracted style guide if one exists.

---

### `/pr-pitching:build-media-list`
**Build a tiered, scored, prioritized contact list across journalists, influencers, podcasters, newsletter authors, analysts, and community moderators.**

Goes beyond traditional media lists to include all relevant contact types for modern PR campaigns. Recommends the right contact mix for your announcement type, researches and scores each contact on a 1–5 relevance scale using type-specific criteria, assigns Tier A / B / C designations, and produces deep-dives on top-priority targets. Uses engagement rate (not just follower count) for influencer scoring. Only contacts scoring 3+ are pitched — everything below is flagged as noise.

---

### `/pr-pitching:draft-pitch`
**Write personalized pitch emails by tier and beat, with subject line options.**

Drafts Tier A pitches with full personalization and references to the journalist's recent work, Tier B pitches with tailored angles, and Tier C adapted templates. Automatically runs a quality check (scored 1–10) on every pitch before delivery — pitches that fail their own quality check are revised internally before you see them. Length targets: Tier A 200–300 words, Tier B 100–175 words, Tier C 75–125 words.

---

### `/pr-pitching:subject-lines`
**Generate and optimize email subject lines specifically for media pitches.**

Produces multiple subject line options per pitch, scores each against professional criteria (under 60 characters, specific not clever, no forbidden phrases), and explains the tradeoffs. The rule encoded here: a subject line that tells the journalist exactly what the story is outperforms a clever subject line every time.

---

### `/pr-pitching:follow-up`
**Draft follow-up sequences with correct timing and tone.**

Generates follow-up emails at the right intervals — first follow-up at 2–3 days, second at 4–5 days — with language calibrated to maintain relationship capital rather than burn it. Hard limit of 2 follow-ups per contact enforced. Follow-ups add new information or a different angle rather than simply restating the original pitch.

---

### `/pr-pitching:coverage-tracker`
**Log and analyze campaign coverage with quantified outcomes.**

Processes coverage items (paste a list or upload a file) and produces a full campaign report: total placements, estimated reach, tier breakdown, platform breakdown, tone analysis, message penetration rates, top 5 placements by reach, and amplification priorities. Generates an executive-ready narrative summary suitable for leadership reporting. Flags any negative coverage or factual errors requiring response.

---

### `/pr-pitching:campaign-brief`
**Compile all campaign work into a professional Word document deliverable.**

Produces a structured 10-section campaign brief in Word format — available as a pre-campaign planning document or post-campaign results report. Includes news value assessment, positioning rationale, media strategy, outreach results, coverage analysis, and recommendations for the next campaign. Suitable for client delivery or executive presentation.

---

### `/pr-pitching:learn-style`
**Upload historical press releases and generate a custom style guide and template in one step.**

Upload 5–10 releases in any format (Word, PDF, plain text, Google Docs export). Claude reads every file directly — no conversion tools needed — and analyzes style across 13 dimensions: headline patterns, header block format, lead paragraph structure, body structure, data presentation, quote style, vocabulary and tone, boilerplate, contact block, special cases, readability profile, sentiment profile, and vocabulary metrics including estimated grade level and technical density. Outputs both a human-reviewable style guide and a fill-in-the-blanks template that reflects your actual format, not a generic one.

---

## Skills (Auto-Applied)

Skills load automatically and apply without explicit commands. Claude draws on them based on context.

| Skill | What It Encodes |
|---|---|
| `pr-strategy` | News value hierarchy, USP framework, pitch quality standards, relationship capital philosophy |
| `pr-competitive-analysis` | Competitive frame definition, gap analysis, differentiation identification |
| `pr-release-review` | 9-element structural checklist, key messages audit, red flag patterns |
| `pr-journalist-intel` | Full contact type taxonomy, relevance scoring, platform categorization, relationship intelligence |
| `pr-journalist-scoring` | Type-specific 1–5 scoring criteria for journalists, influencers, podcasters, analysts, and more |
| `pr-pitch-drafting` | Pitch anatomy, length guidelines by tier, personalization standards, hook requirements |
| `pr-pitch-analysis` | Quality evaluation criteria, rule-based checks, scoring verdict framework |
| `pr-outreach-execution` | Exclusivity vs. embargo strategy, timing by outlet type, sequencing and embargo management |
| `pr-coverage-tracking` | Coverage logging standards, metrics definitions, data collection framework |
| `pr-coverage-analysis` | Quantified outcomes calculation, message penetration, executive reporting standards |
| `pr-campaign-brief` | 10-section report structure for pre and post-campaign Word deliverables |
| `pr-org-context` | **Your organization's details** — customize this before first use |
| `pr-style-guide` | Loads extracted style guide and applies it to all press release drafts |

---

## Quality Standards Built In

The plugin enforces professional discipline at every step — not as suggestions, but as hard constraints:

- News value assessed across 14 criteria before pitching is recommended
- Primary USP must be specific and defensible before pitch drafting begins
- Contact relevance score of 3+ required for pitching — below 3 is flagged "Do Not Pitch"
- Tier A contacts receive fully personalized pitches with references to their recent work
- Subject lines enforced under 60 characters; forbidden phrases blocked
- Pitches must lead with the news hook — company background in the opening is flagged and rewritten
- Every generated pitch is auto quality-checked (scored 1–10) before delivery
- Maximum 2 follow-ups per contact; correct timing intervals applied
- Coverage reported with quantified outcomes — reach, sentiment, message penetration rates
- Honest reporting standard: if a campaign underperformed, the report says so with specific recommendations

---

## Customization

**Essential — do this first:**
Edit `skills/pr-org-context/SKILL.md` with your organization's boilerplate, spokespeople, key messages, media contacts, warm journalist relationships, sensitive topics, and brand voice.

**High value — do this second:**
Run `/pr-pitching:learn-style` with 5–10 historical releases. The extracted style guide and template make every future draft sound like you wrote it.

**Optional:**
Any skill or command file can be edited to adjust thresholds, preferences, or standards for your organization. They're markdown files — no code required.

---

## File Structure

```
pr-pitching/
├── .claude-plugin/
│   └── plugin.json
├── skills/                      # 13 auto-applied skill directories
│   ├── pr-strategy/SKILL.md
│   ├── pr-competitive-analysis/SKILL.md
│   ├── pr-release-review/SKILL.md
│   ├── pr-journalist-intel/SKILL.md
│   ├── pr-journalist-scoring/SKILL.md
│   ├── pr-pitch-drafting/SKILL.md
│   ├── pr-pitch-analysis/SKILL.md
│   ├── pr-outreach-execution/SKILL.md
│   ├── pr-coverage-tracking/SKILL.md
│   ├── pr-coverage-analysis/SKILL.md
│   ├── pr-campaign-brief/SKILL.md
│   ├── pr-org-context/SKILL.md  ← CUSTOMIZE THIS FIRST
│   └── pr-style-guide/SKILL.md
├── commands/                    # 10 explicit workflow commands
│   ├── assess-news-value.md
│   ├── competitive-scan.md
│   ├── review-release.md
│   ├── build-media-list.md
│   ├── draft-pitch.md
│   ├── subject-lines.md
│   ├── follow-up.md
│   ├── coverage-tracker.md
│   ├── campaign-brief.md
│   └── pr-learn-style.md
├── examples/                    # Generated by /pr-pitching:learn-style
│   ├── style-guide-extracted.md
│   └── press-release-template.md
├── LICENSE
└── README.md
```

---

## Requirements

- Claude Desktop (macOS or Windows)
- Claude Cowork tab (available on Pro, Max, Team, and Enterprise plans)
- No other dependencies

---

## Philosophy

Volume is the enemy. Twenty well-targeted journalists outperform two hundred spray-and-pray every time. Every pitch must answer the journalist's implicit question: *"Why would my readers care?"*

This plugin is built to enforce that discipline at every step — from the moment you assess whether your announcement is actually newsworthy through the moment you report results to leadership. The expertise encoded here comes from 25+ years of Fortune 100 strategic communications. It's not a template library. It's a way of thinking about PR that happens to run in Claude.

---

## License

Copyright (c) 2026. Personal and evaluation use only. Commercial use, redistribution, or resale requires written permission. See [LICENSE](./LICENSE) for full terms.

---

## Contributing

Found a bug, have a suggestion, or want to extend the plugin for your industry? Open an issue or submit a pull request. The plugin is markdown files — no code background required to contribute.
