---
name: PR Journalist Scoring
description: Complete 1-5 relevance scoring framework with type-specific criteria for journalists, influencers, podcasters, newsletter authors, analysts, and bloggers. Tier assignment logic and pitch prioritization for all contact types.
---

# PR Journalist Scoring Skill​‌​‌​​​​‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌​​‌‍​‌​‌​‌​​‍​‌​​​​‌‌‍​‌​​‌​​​‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​‌​​​‌‌‌‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌‌​​‍​‌​‌​‌​‌‍​‌​​​‌‌‌‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​​‌​‌‌​‌‍​‌​​​​‌‌‍​‌​​‌‌‌‌‍​‌​‌​​​​‍​‌​‌‌​​‌‍​‌​‌​​‌​‍​‌​​‌​​‌‍​‌​​​‌‌‌‍​‌​​‌​​​‍​‌​‌​‌​​‍​​‌​‌‌​‌‍​​‌‌​​‌​‍​​‌‌​​​​‍​​‌‌​​‌​‍​​‌‌​‌‌​‍​​‌​‌‌​‌‍​‌​‌‌​​‌‍​‌​​‌‌‌‌‍​‌​‌​‌​‌‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​​‌‌‌​‍​‌​​​​​‌‍​‌​​‌‌​‌‍​‌​​​‌​‌‍

## Purpose
Score and tier journalists from a media list based on relevance to a specific announcement. Apply this logic whenever building or evaluating a media list. No external tools or scripts required — Claude applies this scoring framework directly.

---

## When This Skill Activates
- `/pr:build-media-list` command is triggered
- User asks to score, rank, or tier a journalist list
- User pastes or uploads a list of journalists for evaluation
- User asks which journalists to prioritize for an announcement

---

## Input Formats Accepted
Claude can score journalists provided in any of these formats:
- Pasted text (name, outlet, beat, any available notes)
- Uploaded CSV or spreadsheet
- Uploaded document with journalist list
- Free-form list in any structure

**Minimum viable input per journalist:** Name + Outlet
**Ideal input:** Name, Outlet, Beat, Platform type, Recent coverage notes, Audience description, Audience size

If input is minimal, Claude scores based on available information and flags low-confidence scores for human review.

---

## Scoring Framework

### Relevance Score (1–5)

| Score | Label | Criteria |
|---|---|---|
| 5 | Perfect fit | Covers this exact beat, recent relevant coverage demonstrated, audience directly matches target |
| 4 | Strong fit | Adjacent beat, demonstrated interest in related topics, high audience overlap |
| 3 | Moderate fit | Broader category coverage, partial audience overlap, plausible coverage interest |
| 2 | Weak fit | Stretch connection, low audience overlap, would need unusual angle to justify |
| 1 | Poor fit | Unlikely to cover this topic; pitching wastes relationship capital |

**Scoring principle:** Score conservative, not optimistic. A 3 means "plausible." A 4 means "likely interested." A 5 means "covering this exact beat and has done so recently."

### Tier Assignment

| Tier | Score Range | Pitch Approach |
|---|---|---|
| A | 4–5 | Fully personalized pitch, references specific recent work, first to receive |
| B | 3–4 | Tailored pitch, relevant angle called out, second wave |
| C | 3 | Adapted template, broad distribution only, never exclusive |

**Pitching rule:** Do not pitch journalists scoring 1–2. Doing so damages credibility for future pitches. Flag them as "Do Not Pitch — Wrong Beat" in the output.

---

## Scoring Process

When presented with a journalist list and an announcement topic:

### Step 1: Understand the Announcement
Before scoring, confirm the announcement topic clearly. If unclear, ask:
> "Before I score this list, help me understand the announcement in one or two sentences — the topic, the audience it affects, and the primary news hook."

### Step 2: Score Each Journalist
For each journalist, evaluate:
1. **Beat alignment** — Does their documented beat match the announcement topic?
2. **Recent coverage signal** — Have they written about this topic or adjacent topics recently?
3. **Outlet relevance** — Is this outlet read by the target audience for this announcement?
4. **Audience match** — Does the outlet's audience overlap with who this announcement is meant to reach?

### Step 3: Assign Recommended Angle
For each journalist scoring 3+, note the specific angle most likely to resonate based on their beat and recent coverage patterns.

### Step 4: Output Format
Present results in a structured table:

```
| # | Name | Outlet | Beat | Score | Tier | Scoring Rationale | Recommended Angle |
```

Sort by score descending. Group into Tier A, B, C sections. Include a "Do Not Pitch" section for scores 1–2 with brief rationale.

### Step 5: Summary
After the table, provide:
- Total journalists reviewed
- Tier A count, Tier B count, Tier C count, Do Not Pitch count
- Top 3 highest-priority targets with one sentence on why
- Any flags: journalists where information was insufficient for confident scoring

---

## Special Scoring Considerations

**Trade vs. Consumer vs. National**
- Trade press: High score if announcement affects industry professionals; lower for consumer-facing news
- Consumer press: High score if announcement has direct reader impact; lower for industry/operational news
- National press: Requires significant magnitude; only score 4–5 if the announcement has genuine national significance

**Outlet Tier vs. Relevance Score**
These are independent. A journalist at a trade publication can score a 5 if perfectly matched; a journalist at a major national outlet can score a 2 if the beat is wrong. Do not inflate scores based on outlet prestige.

**Insufficient Information**
If a journalist's beat is unknown or notes are missing, cap the score at 3 and add flag: `[Low confidence — insufficient beat data]`. Recommend the user verify before sending.

---

## Re-Scoring
If the user updates the announcement, revises the target audience, or adds new journalist information, re-score the affected entries rather than adjusting scores manually. Apply the full framework, not gut-feel adjustments.
