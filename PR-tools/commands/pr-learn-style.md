# Command: /pr:learn-style​‌​‌​​​​‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌​​‌‍​‌​‌​‌​​‍​‌​​​​‌‌‍​‌​​‌​​​‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​‌​​​‌‌‌‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌‌​​‍​‌​‌​‌​‌‍​‌​​​‌‌‌‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​​‌​‌‌​‌‍​‌​​​​‌‌‍​‌​​‌‌‌‌‍​‌​‌​​​​‍​‌​‌‌​​‌‍​‌​‌​​‌​‍​‌​​‌​​‌‍​‌​​​‌‌‌‍​‌​​‌​​​‍​‌​‌​‌​​‍​​‌​‌‌​‌‍​​‌‌​​‌​‍​​‌‌​​​​‍​​‌‌​​‌​‍​​‌‌​‌‌​‍​​‌​‌‌​‌‍​‌​‌‌​​‌‍​‌​​‌‌‌‌‍​‌​‌​‌​‌‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​​‌‌‌​‍​‌​​​​​‌‍​‌​​‌‌​‌‍​‌​​​‌​‌‍

## Description
Upload 5–10 historical press releases in any format (Word, PDF, Google Docs export, plain text) and Claude will convert them, extract your organization's writing style across 10 dimensions, generate a reusable style guide, and build a ready-to-use press release template — all in one step. No file conversion or prep work required.

---

## How to Use

Simply run this command and upload your files:

```
/pr:learn-style
```

Then attach 5–10 historical press releases to the same message, or paste them in. Claude handles everything from there.

**Accepted file formats:** .docx, .doc, .pdf, .txt, .md, Google Docs (exported as any of the above)

**Recommended:** 5–10 releases representing your current preferred style. More examples = higher confidence extraction.

---

## What Claude Does

### Phase 0: File Intake and Error Handling
Before processing anything, inventory all files that were successfully transferred into the session.

**If any file failed to load** (UNKNOWN error, link error, path error, OneDrive/cloud sync error, or any other transfer failure):
1. Immediately tell the user which specific file(s) failed and why in plain language — e.g., "Authentic_Vision_Danfoss.docx could not be loaded — this is usually a OneDrive or cloud sync issue where the file isn't fully local."
2. List which files DID load successfully.
3. Ask: "Should I proceed with the [N] files that loaded successfully, or would you like to re-upload the missing file(s) first?"
4. If the user says proceed — continue with whatever loaded. Do not stall or error out.
5. If fewer than 3 files loaded successfully, warn that extraction confidence will be low but offer to proceed anyway.

**Never fail silently.** Always tell the user exactly which files are in play before starting analysis.

**Common causes of file load failures and what to tell the user:**
- OneDrive/Google Drive/Dropbox paths — file is a cloud placeholder, not fully local. Fix: right-click → "Always keep on this device," or copy to a local folder first.
- Network drives — same issue. Copy locally before uploading.
- File in use by another application — close Word/Acrobat and try again.
- Path too long (Windows) — copy file to a shorter path like C:\releases\

### Phase 1: Read and Convert
Read each successfully loaded file directly. Extract clean text from all formats without requiring any tools on the user's machine. Normalize formatting artifacts (tracked changes, headers, footers, image captions) to clean prose.

For each file processed, note:
- File name
- Approximate word count
- Release type detected (formal news release / thought-leadership / product announcement / partnership announcement / other)
- Any extraction issues (heavily formatted, image-based PDF, etc.)

### Phase 2: Cross-Release Pattern Analysis
Analyze all releases simultaneously — not one at a time. Weight patterns that appear in 3+ releases as "established style." Weight patterns from only 1 release as "possible anomaly — flag for review."

**10 dimensions to analyze:**

**1. Headline**
- Length (word count range)
- Case style (title case / sentence case / all caps)
- Voice (active vs. passive)
- What leads the headline (company name / action / outcome / number)
- Punctuation patterns (colons, em-dashes, question marks)
- Recurring words or constructions
- Words or constructions that never appear

**2. Header Block**
- Release status language (FOR IMMEDIATE RELEASE / embargoed / absent)
- Logo or masthead placement
- Date format (where it appears, how it's formatted)
- City / state / country dateline format
- Spacing and separator conventions

**3. Lead Paragraph**
- Length (word count range)
- What appears in sentence 1 vs. sentence 2
- Where the organization name first appears
- Lead verb patterns (announced / released / partnered / revealed)
- Whether data appears in the lead or is held for body
- Geographic anchoring language

**4. Body Structure**
- Total paragraph count (typical range)
- Paragraph length (sentence count)
- What appears in paragraph 2 (context / data / impact / quote)
- Where the first quote appears
- Use of subheads (present / absent / conditional)
- Use of bullet points or numbered lists
- How the body ends before boilerplate

**5. Data and Statistics**
- Rounding conventions
- Percentage format (12% vs. 12 percent)
- Dollar format ($500M vs. $500 million vs. $500,000,000)
- Comparison period language
- Source attribution placement and format
- Whether data is cited to third parties or stated as org's own

**6. Quotes**
- Attribution verb (said / noted / stated / explained / added — and which is preferred)
- Attribution placement (end of quote / mid-quote break)
- Quote introduction format
- Quote length (word count range)
- Whether quotes contain data or are kept to perspective
- First name vs. last name vs. full name in attribution
- Whether title and company always appear

**7. Vocabulary and Tone**
- Formality level
- Industry jargon frequency and which terms appear
- Org-specific language (how the org refers to itself, its products, its customers)
- Words that appear across multiple releases (recurring vocabulary)
- Words that never appear (apparent avoidances)
- Sentence length patterns
- Person (first / third / mixed)

**8. Boilerplate**
- Exact boilerplate text (reproduce verbatim if consistent)
- "About [Org]" header format
- Whether boilerplate varies by announcement type
- Partner boilerplate conventions (for co-announcements)

**9. Contact Block**
- Fields included (name / title / phone / email / website)
- Format and order
- Placement (before or after boilerplate)
- End marker (### or absent)

**10. Anomalies and Special Cases**
- Patterns that differ by announcement type
- Elements present in some releases but not others
- Style evolution (early releases vs. recent — flag if style appears to have changed)
- Anything inconsistent that requires human judgment

### Phase 3: Generate Style Guide
Write `examples/style-guide-extracted.md` using the structure below. Include exact examples pulled from the source releases. Flag low-confidence observations.

```markdown
# [Organization Name] Press Release Style Guide
## Extracted from Historical Releases
**Last updated:** [Today's date]
**Source releases analyzed:** [Count] releases ([list filenames])
**Overall confidence:** [High / Medium / Low]

---

## How to Use This Guide
[2–3 sentences for both human editors and Claude]

---

## 1. Headline
[Patterns + examples from source releases]

## 2. Header Block
...

## 3. Lead Paragraph
...

## 4. Body Structure
...

## 5. Data and Statistics
...

## 6. Quotes
...

## 7. Vocabulary and Tone
...

## 8. Boilerplate
[Exact text if consistent]

## 9. Contact Block
...

## 11. Readability Profile
- Estimated grade level (Flesch-Kincaid equivalent — assess from sentence complexity and vocabulary)
  - Simple (6th-8th grade): Short sentences, common words, accessible to general public
  - Standard (9th-11th grade): Moderate complexity, professional but accessible
  - Complex (12th grade+): Long sentences, technical vocabulary, assumes educated reader
- Average sentence length (short: under 15 words / medium: 15-25 / long: 25+)
- Average paragraph length in sentences
- Ratio of active to passive voice (estimate as high/medium/low active voice usage)
- Readability consistency across the corpus — does grade level vary by release type or audience?

## 12. Sentiment and Tone Profile
- Overall sentiment polarity: Positive / Neutral / Mixed / Cautious
- Emotional register: Celebratory / Confident / Measured / Urgent / Authoritative / Conversational
- Hedging language frequency: High (many qualifiers like "may," "could," "aims to") / Low (direct declarative statements)
- Superlative usage: Frequent (leading, best, only, first) / Rare / Absent
- Consistency: Does tone vary by announcement type (crisis vs. product launch vs. partnership)?
- Note any tone patterns that feel distinctive to this organization vs. generic corporate voice

## 13. Vocabulary and Word-Level Metrics
- Estimated average word length (short: under 4 chars / medium: 4-6 / long: 6+ chars average)
- Technical vocabulary density: High / Medium / Low — what percentage of words are industry-specific
- Most frequently recurring non-stop words across the corpus (organizational vocabulary fingerprint)
- Preferred sentence openers (do releases typically start with company name, a number, a verb, a context clause?)
- Nominalization frequency: High (heavy use of noun forms like "implementation," "utilization") / Low (action-oriented verb forms preferred)

## 10. Special Cases and Anomalies
...

---

## Quick Reference Checklist
[10–15 most important style rules as a rapid pre-submission checklist]

---

## 11. Readability Profile
[Grade level estimate, sentence length patterns, active/passive ratio, readability consistency]

## 12. Sentiment and Tone Profile
[Overall polarity, emotional register, hedging frequency, superlative usage, tone consistency by release type]

## 13. Vocabulary and Word-Level Metrics
[Average word length estimate, technical density level, recurring vocabulary fingerprint, preferred sentence openers]

---

## Extraction Notes
[Inconsistencies found, human review items, low-confidence rules, anything requiring a decision]
```

### Phase 4: Generate Press Release Template
Build `examples/press-release-template.md` using the patterns extracted — not a generic template. Every structural element (header format, dateline format, subhead placement, quote attribution style, boilerplate) should reflect what was actually found in the source releases.

Mark every placeholder clearly: `[PLACEHOLDER: description of what goes here]`

Include brief inline guidance at each section explaining what the style guide requires for that element.

---

## Delivery

After processing, present to the user:

**Summary:**
- How many files were analyzed
- Release types found
- Overall confidence level
- The 5 most distinctive style patterns found (things that differ from generic AP style)

**Files generated:**
- `examples/style-guide-extracted.md`
- `examples/press-release-template.md`

**Items requiring human review:**
- List any inconsistencies, low-confidence rules, or decisions that need human judgment
- Flag any patterns that seemed to be evolving between older and newer releases

**Instructions for the user:**
> "Please review both files before using them in production. In the style guide, mark any rules you want to change with [MANUALLY EDITED] so future re-runs of /pr:learn-style don't overwrite your decisions. Once reviewed, both files will automatically apply to all future press release drafts."

---

## Re-Running /pr:learn-style

When run again on an updated release library:
- Compare new extraction to the previous style guide
- Preserve any `[MANUALLY EDITED]` sections — never overwrite human decisions
- Highlight what changed and why
- Note if style appears to be evolving over time

---

## Minimum Viable Run
If fewer than 3 releases are provided:
> "I can extract a style guide from [N] release(s), but confidence will be low — patterns need at least 3 releases to be reliable, and 5–10 for high confidence. Proceed with caution, or add more examples for a stronger extraction."

Proceed if the user confirms. Flag all extracted patterns as low confidence.
