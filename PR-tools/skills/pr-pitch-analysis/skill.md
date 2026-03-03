# PR Pitch Analysis Skill​‌​‌​​​​‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌​​‌‍​‌​‌​‌​​‍​‌​​​​‌‌‍​‌​​‌​​​‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​‌​​​‌‌‌‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌‌​​‍​‌​‌​‌​‌‍​‌​​​‌‌‌‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​​‌​‌‌​‌‍​‌​​​​‌‌‍​‌​​‌‌‌‌‍​‌​‌​​​​‍​‌​‌‌​​‌‍​‌​‌​​‌​‍​‌​​‌​​‌‍​‌​​​‌‌‌‍​‌​​‌​​​‍​‌​‌​‌​​‍​​‌​‌‌​‌‍​​‌‌​​‌​‍​​‌‌​​​​‍​​‌‌​​‌​‍​​‌‌​‌‌​‍​​‌​‌‌​‌‍​‌​‌‌​​‌‍​‌​​‌‌‌‌‍​‌​‌​‌​‌‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​​‌‌‌​‍​‌​​​​​‌‍​‌​​‌‌​‌‍​‌​​​‌​‌‍

## Purpose
Evaluate pitch email drafts against professional quality criteria before they go to journalists. Apply this framework whenever reviewing, scoring, or improving a pitch. No external tools required — Claude applies this analysis directly.

---

## When This Skill Activates
- `/pr:draft-pitch` command produces a pitch draft (auto-apply before delivering)
- User asks Claude to review, critique, or improve a pitch
- User pastes a pitch and asks if it's ready to send
- User asks for a quality check before outreach begins

---

## The Core Question
Before any detailed scoring, answer this one question:
> **"Would a busy journalist who gets 200 pitches a week stop reading after the first two sentences?"**

If no — identify exactly why not and fix it before scoring anything else.

---

## Rule-Based Checks (Apply First — Fast Filters)

These are hard disqualifiers. If any trigger, flag immediately before deeper analysis.

### Subject Line Rules
| Rule | Standard |
|---|---|
| Length | Under 60 characters preferred; 60–70 acceptable; over 70 problematic |
| Forbidden phrases | "press release," "for immediate release," "exciting," "revolutionary," "game-changing," "just checking in," "following up," "important announcement," "exclusive opportunity," "breaking news" |
| Forbidden formats | Do not start with Re: or Fw: |
| Tone | Specific over clever. A subject that tells the journalist exactly what the story is outperforms a clever subject every time |

### Body Opening Rules
| Rule | Standard |
|---|---|
| Forbidden openers | "My name is...," "I hope this email finds you well," "I wanted to reach out," "I am writing to...," "Please find attached," "I hope you're doing well" |
| Lead requirement | First sentence must contain the news hook — not company background, not pleasantries, not context-setting |
| Company intro ban | Do not open with company history, founding date, product description, or "is proud to announce" |

### Length Rules
| Tier | Target Length |
|---|---|
| Tier A | 200–300 words |
| Tier B | 100–175 words |
| Tier C | 75–125 words |
| Hard ceiling | 350 words — any pitch over this needs cuts, not edits |

### Ask Rules
Every pitch must contain a specific, actionable ask. Acceptable asks:
- Request for a call or interview
- Offer of an exclusive
- Invitation to a briefing or event
- Request for a response or comment

A pitch that ends without a clear ask is incomplete.

---

## Quality Dimensions (Apply After Rule Checks)

Score each dimension and provide one-sentence rationale:

### 1. Hook Quality — Strong / Moderate / Weak
- **Strong:** First sentence is newsworthy, specific, and would make a journalist want to know more
- **Moderate:** News is present but buried or diluted by surrounding language
- **Weak:** First sentence is about the company, the product, or context rather than the news

### 2. Personalization Signal — Present / Generic / Missing
- **Present:** References a specific article the journalist wrote, their beat, or their publication's audience explicitly
- **Generic:** Has a journalist name in the salutation but nothing else specific
- **Missing:** No indication this pitch was written for this journalist at all

### 3. USP Clarity — Clear / Vague / Missing
- **Clear:** The one thing that makes this news unique is stated explicitly and is defensible
- **Vague:** There's something distinctive implied but not stated
- **Missing:** This could be any company's announcement; nothing differentiates it

### 4. Tone — Professional / Too Formal / Too Casual / Marketing-Speak
- **Professional:** Reads like a colleague briefing a journalist, not a sales pitch or a press conference
- **Too Formal:** Stilted, bureaucratic, sounds like it came from a legal department
- **Too Casual:** Inappropriate familiarity for a cold or warm professional outreach
- **Marketing-Speak:** Loaded with superlatives, buzzwords, and unverifiable claims

### 5. Newsworthiness Signal — Strong / Moderate / Weak
- **Strong:** Reader of this pitch could immediately see why their audience would care
- **Moderate:** News value is present but requires inference
- **Weak:** This pitch describes a product or company, not a story

---

## Overall Score (1–10) and Verdict

| Score | Verdict |
|---|---|
| 9–10 | ✅ Ready to send |
| 7–8 | ⚡ Send after minor revisions (list specific fixes) |
| 5–6 | 🔄 Needs revision before sending (structural issues) |
| 1–4 | ❌ Significant rework needed (fundamental problems) |

---

## Output Format

When analyzing a pitch, deliver:

1. **Rule check results** — flag any hard violations immediately
2. **Dimension scores** — table format with one-line rationale each
3. **Overall score and verdict**
4. **Top 3 specific improvements** — actionable, in priority order
5. **Strongest element** — what's already working
6. **Recommended subject line** — if current subject fails checks, provide a replacement

---

## Auto-Apply After Drafting

Whenever Claude drafts a pitch via `/pr:draft-pitch`, run this analysis silently before delivering the draft. If the draft scores below 7 or triggers any rule violations, revise internally before presenting it. Do not deliver a pitch that would fail its own quality check.

When delivering a draft, include a brief quality summary at the bottom:
```
Quality check: [Score]/10 — [Verdict]
Subject: [character count] chars
Length: [word count] words
```
