# PR Pitching Plugin for Claude Cowork​‌​‌​​​​‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌​​‌‍​‌​‌​‌​​‍​‌​​​​‌‌‍​‌​​‌​​​‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​‌​​​‌‌‌‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌‌​​‍​‌​‌​‌​‌‍​‌​​​‌‌‌‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​​‌​‌‌​‌‍​‌​​​​‌‌‍​‌​​‌‌‌‌‍​‌​‌​​​​‍​‌​‌‌​​‌‍​‌​‌​​‌​‍​‌​​‌​​‌‍​‌​​​‌‌‌‍​‌​​‌​​​‍​‌​‌​‌​​‍​​‌​‌‌​‌‍​​‌‌​​‌​‍​​‌‌​​​​‍​​‌‌​​‌​‍​​‌‌​‌‌​‍​​‌​‌‌​‌‍​‌​‌‌​​‌‍​‌​​‌‌‌‌‍​‌​‌​‌​‌‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​​‌‌‌​‍​‌​​​​​‌‍​‌​​‌‌​‌‍​‌​​​‌​‌‍
**Version 3.0 | Zero dependencies | Works entirely within Claude**

*Copyright (c) 2026 Robert Carlton, RMCmailbox3+PRTOOLS@gmail.com. Personal and evaluation use only. See LICENSE for terms.*

A complete press release drafting, writing, evaluating and pitching tool leveraging deep communications expertise and AI into structured, repeatable workflows. Everything runs through Claude — no Python environment, no API keys, no local setup required.

---

## Quick Start

### Step 1: Customize Your Org Context
Open `skills/pr-org-context.md` and fill in your organization's details:
- Boilerplate text
- Spokespeople with titles
- Key messages (standing and campaign-specific)
- Media contact information
- Warm journalist relationships
- Sensitive topics and guidance

This is the most important customization step. Everything else works without it, but org context makes every output specific to you.

### Step 2: Install the Plugin
```
claude plugins add /path/to/pr-tools
```

### Step 3: Load Your Writing Style (Optional but Recommended)
Run `/pr:learn-style` and upload 5–10 historical press releases in any format (Word, PDF, plain text). Claude converts them, extracts your style across 10 dimensions, and generates both a style guide and a fill-in-the-blanks template. Takes about 2 minutes. No prep work required.

### Step 4: Run Your First Campaign
```
/pr:assess-news-value
```
Paste your announcement and get an honest news value assessment before you write a word.

---

## How It Works

The plugin loads automatically when you start a Claude Cowork session. Skills activate based on context — you don't need to reference them explicitly. Commands are triggered with `/pr:` prefixes.

**Skills** = background expertise Claude applies automatically
**Commands** = explicit workflow steps you trigger when ready

---

## Commands

| Command | What It Does |
|---|---|
| `/pr:assess-news-value` | Score your announcement against 6 newsworthiness criteria before committing to a campaign |
| `/pr:competitive-scan` | Research comparable announcements, identify your USP, sharpen positioning |
| `/pr:review-release` | Audit or draft a press release against structural standards and key messages |
| `/pr:build-media-list` | Research journalists, score relevance 1–5, assign tiers with rationale |
| `/pr:draft-pitch` | Write personalized pitches by tier and beat, with subject line options |
| `/pr:subject-lines` | Optimize subject lines specifically (under 60 chars, specific not clever) |
| `/pr:follow-up` | Draft follow-up sequences (day 2–3, day 4–5, max 2 follow-ups total) |
| `/pr:coverage-tracker` | Log and analyze campaign coverage with quantified outcomes |
| `/pr:campaign-brief` | Compile all work into a Word document deliverable |
| `/pr:learn-style` | Upload historical releases and get a custom style guide + template in one step |

---

## Skills (Auto-Applied)

| Skill | What It Encodes |
|---|---|
| `pr-strategy.md` | News value hierarchy, USP framework, pitch quality standards, relationship capital |
| `pr-competitive-analysis.md` | Competitive frame definition, gap analysis, differentiation identification |
| `pr-release-review.md` | 9-element structure checklist, key messages audit, red flags |
| `pr-journalist-intel.md` | Relevance scoring system, platform categorization, relationship intelligence |
| `pr-journalist-scoring.md` | Complete 1–5 scoring framework, tier assignment logic, pitch prioritization |
| `pr-pitch-drafting.md` | Anatomy of effective pitches, length guidelines by tier, personalization standards |
| `pr-pitch-analysis.md` | Quality evaluation criteria, rule-based checks, verdict framework |
| `pr-outreach-execution.md` | Exclusivity vs. embargo strategy, timing by outlet type, sequencing |
| `pr-coverage-tracking.md` | Coverage logging standards, metrics definitions |
| `pr-coverage-analysis.md` | Quantified outcomes calculation, message penetration, executive reporting |
| `pr-campaign-brief.md` | 10-section report structure, pre and post-campaign formats |
| `pr-org-context.md` | Your organization's details — customize this |
| `pr-style-guide.md` | Loads extracted style guide, applies to all drafts |

---

## The Style Learning Workflow

Run `/pr:learn-style` and upload 5–10 releases in any format. Claude reads every file directly, converts internally, analyzes all releases simultaneously, and produces two files:

- `examples/style-guide-extracted.md` — explicit style rules with source examples
- `examples/press-release-template.md` — fill-in-the-blanks template matching your actual format

Review both files before production use. Mark any corrections with [MANUALLY EDITED] — future re-runs will not overwrite those sections.

---

## Quality Standards Built In

- News value assessed before pitching (6 criteria, scored High/Medium/Low)
- Primary USP required before pitch drafting (specific and defensible)
- Journalist relevance score 3+ required for pitching (1–2 = do not pitch)
- Tier A journalists get fully personalized pitches with recent work references
- Subject lines under 60 characters, specific not clever
- Pitches lead with news hook — never company background
- Auto quality check on every generated pitch (scored 1–10 with verdict)
- Maximum 2 follow-ups per journalist, 2–3 days then 4–5 days spacing
- Coverage tracked with quantified outcomes (reach, sentiment, message penetration)

---

## File Structure

```
pr-pitching/
├── .claude-plugin/
│   └── plugin.json
├── skills/                      (13 files)
│   ├── pr-org-context.md        ← CUSTOMIZE THIS FIRST
│   └── [12 other skill files]
├── commands/                    (10 files)
│   └── [10 command files]
└── examples/                    (generated by /pr:learn-style)
    ├── style-guide-extracted.md
    └── press-release-template.md
```

---

## Recommended First Session

1. Customize `pr-org-context.md`
2. Run `/pr:learn-style` and upload 5–10 historical releases
3. Review generated style guide and template, mark any edits `[MANUALLY EDITED]`
4. Run `/pr:assess-news-value` with a real announcement
5. Run through one complete campaign workflow end to end

---

## Philosophy

Volume is the enemy. Twenty well-targeted journalists outperform two hundred spray-and-pray every time. Every pitch must answer the journalist's implicit question: "Why would my readers care?" The plugin enforces this discipline at every step — from news value assessment through coverage reporting.
