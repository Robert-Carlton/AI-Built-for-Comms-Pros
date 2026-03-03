# PR Coverage Analysis Skill​‌​‌​​​​‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌​​‌‍​‌​‌​‌​​‍​‌​​​​‌‌‍​‌​​‌​​​‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​‌​​​‌‌‌‍​​‌​‌‌​‌‍​‌​‌​​​​‍​‌​​‌‌​​‍​‌​‌​‌​‌‍​‌​​​‌‌‌‍​‌​​‌​​‌‍​‌​​‌‌‌​‍​​‌​‌‌​‌‍​‌​​​​‌‌‍​‌​​‌‌‌‌‍​‌​‌​​​​‍​‌​‌‌​​‌‍​‌​‌​​‌​‍​‌​​‌​​‌‍​‌​​​‌‌‌‍​‌​​‌​​​‍​‌​‌​‌​​‍​​‌​‌‌​‌‍​​‌‌​​‌​‍​​‌‌​​​​‍​​‌‌​​‌​‍​​‌‌​‌‌​‍​​‌​‌‌​‌‍​‌​‌‌​​‌‍​‌​​‌‌‌‌‍​‌​‌​‌​‌‍​‌​‌​​‌​‍​​‌​‌‌​‌‍​‌​​‌‌‌​‍​‌​​​​​‌‍​‌​​‌‌​‌‍​‌​​​‌​‌‍

## Purpose
Process media coverage after a campaign, calculate quantified outcomes, assess message penetration, and produce an executive-ready report. No external tools required — Claude applies this analysis directly from coverage data the user provides.

---

## When This Skill Activates
- `/pr:coverage-tracker` command is triggered
- User shares coverage results and asks for analysis
- User asks Claude to summarize, quantify, or report on campaign coverage
- User pastes or uploads a list of articles, placements, or coverage items

---

## Input Formats Accepted
Claude can process coverage provided as:
- Pasted list (outlet name + headline + any available details)
- Uploaded CSV or spreadsheet
- Uploaded document with coverage log
- Free-form notes about coverage received

**Minimum viable input per item:** Outlet name + Headline
**Ideal input per item:** Outlet, Journalist, Platform type, Publication date, URL, Headline, Story type, Tier, Pitched or organic, Key messages present, Tone, Estimated reach, Notes

If reach data is missing for most items, flag this in the report and note that total reach calculations will be incomplete.

---

## Data Fields and Accepted Values

**Story type:** breaking_news | feature | mention | quote_only | negative | neutral
**Tone:** positive | neutral | mixed | negative
**Platform type:** national_print | national_digital | trade | local_regional | broadcast | podcast | newsletter | social
**Tier:** A | B | C
**Pitched or organic:** pitched | organic

---

## Analysis Framework

### Step 1: Parse and Normalize
Read all coverage items and normalize inconsistent entries (e.g., "Positive" → "positive", "Tribune" → ask user to confirm full outlet name if ambiguous).

### Step 2: Calculate Quantified Metrics

**Reach Calculations**
- Sum all estimated_reach values
- Handle formats: 2.5M = 2,500,000 | 450K = 450,000 | 35,000 = 35,000
- Note how many items had reach data vs. total placements
- Flag if more than 30% of items lack reach data

**Placement Totals**
- Total placements
- By platform type
- By tier (A / B / C)
- Pitched vs. organic breakdown
- Organic pickup rate (organic ÷ total × 100)

**Tone Breakdown**
- Count by tone category
- Positive rate (positive ÷ total × 100)
- Negative rate (negative ÷ total × 100)

**Top Placements**
- Top 5 by estimated reach
- Top 3 by coverage quality (feature > mention > quote_only)

### Step 3: Message Penetration Analysis
If key messages were provided, evaluate each coverage item:

For each key message, count:
- How many items included this message explicitly
- How many items included it implicitly or by reference
- How many items missed it entirely
- Message penetration rate (included ÷ total × 100)

If no key messages were provided, ask: "What were the 2–3 key messages you were trying to land? I'll assess how well each one got through."

### Step 4: Sentiment Analysis Per Item
For items where tone was not pre-coded, assess:
- **Positive:** Coverage presents the announcement favorably, org is portrayed well
- **Neutral:** Factual coverage without editorial slant
- **Mixed:** Positive framing alongside critical elements
- **Negative:** Critical framing, challenges raised, unfavorable portrayal

### Step 5: Amplification Priorities
Flag the top 3–5 pieces for active amplification based on:
- High reach + positive tone = highest priority
- Trade publication with message penetration = share internally and with partners
- Feature vs. mention = features warrant more amplification effort

---

## Output Format

Deliver the coverage report in this structure:

---

**CAMPAIGN COVERAGE REPORT**
*[Campaign Name] | [Date Range] | Generated [Today's Date]*

**EXECUTIVE SUMMARY**
[3–4 sentences written for a CEO or Board audience. Specific numbers. Note standout results. Acknowledge any negatives if present. Under 100 words.]

**QUANTIFIED OUTCOMES**
- Total placements: [N]
- Estimated total reach: [N] impressions
- Tier A placements: [N]
- Tier B placements: [N]
- Tier C placements: [N]
- Pitched coverage: [N]
- Organic pickup: [N] ([%] organic rate)

**TONE BREAKDOWN**
- Positive: [N] ([%])
- Neutral: [N] ([%])
- Mixed: [N] ([%])
- Negative: [N] ([%])

**PLACEMENTS BY PLATFORM**
[Platform | Count | % of Total — sorted by count descending]

**MESSAGE PENETRATION**
[Key Message | Landed | Missed | Penetration Rate]
*(If key messages were provided)*

**TOP 5 PLACEMENTS BY REACH**
[Rank | Outlet | Headline | Reach | Tone | Story Type]

**AMPLIFICATION PRIORITIES**
[Top 3–5 pieces to actively amplify, with one-sentence rationale each]

**ITEMS REQUIRING ATTENTION**
[Any negative coverage, factual errors to correct, or follow-up needed]

---

## Honest Reporting Standard
Do not inflate results. If coverage was light, say so. If message penetration was low, quantify it. If most coverage was neutral rather than positive, report it accurately. Leadership needs accurate data to make decisions about future campaigns — optimistic reporting of weak results sets the wrong baseline.

If the campaign underperformed, add a brief "What to do differently" section with 2–3 specific recommendations.
