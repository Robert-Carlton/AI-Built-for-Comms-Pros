# Coverage Tracking Skill

## Purpose
Monitor, log, and analyze media coverage after a press release campaign. Transform coverage data into quantified, reportable outcomes. Support amplification of earned coverage across owned and shared channels.

---

## Coverage Logging

For each piece of coverage secured, record:

| Field | Description |
|-------|-------------|
| Outlet name | Full publication/platform name |
| Journalist | Byline name |
| Platform type | Print / Digital / Broadcast / Podcast / Newsletter / Social |
| Publication date | Date the story ran |
| URL | Link to the story |
| Headline | Exact headline used |
| Story type | Breaking news / Feature / Mention / Quote only / Negative / Neutral |
| Tier | Was this a Tier A, B, or C target? |
| Pitched or organic | Did we pitch this, or did they find it independently? |
| Key messages present | Which of our key messages appeared in the story? |
| Tone | Positive / Neutral / Mixed / Negative |
| Estimated reach | Outlet's average monthly uniques or circulation (use Muck Rack, SimilarWeb, or media kit as reference) |
| Social shares | If available |
| Notes | Any notable angles, omissions, or errors |

---

## Quantified Outcomes Calculation

After coverage is logged, calculate:

**Volume metrics:**
- Total number of placements
- Placements by platform type
- Placements by tier (A/B/C)
- Pitched vs. organic pickup ratio

**Reach metrics:**
- Total estimated impressions (sum of outlet reach figures)
- Top 5 placements by reach
- Broadcast audience reach (if applicable — use Nielsen or station-reported ratings)

**Quality metrics:**
- Key message penetration rate: for each key message, what % of stories included it?
- Tone breakdown: % positive / % neutral / % negative
- Tier A conversion rate: of Tier A journalists pitched, what % produced coverage?
- Exclusive ROI: did the exclusive placement outperform broad distribution targets?

**Share of voice (if competitive tracking is in scope):**
- Our placements vs. competitor placements on the same announcement topic during the same window

---

## Sentiment Analysis Framework

When assessing tone, use these definitions consistently:

- **Positive**: Story leads with our angle, key messages represented accurately, no significant caveats or negative framing
- **Neutral**: Story is factual and accurate but does not adopt our framing; our announcement is one of multiple points
- **Mixed**: Story includes both positive coverage of our announcement and critical or skeptical elements
- **Negative**: Story leads with criticism, challenges our claims, or frames our announcement unfavorably

Always note the reason for any mixed or negative rating — this informs future media relationship strategy.

---

## Amplification Planning

Once coverage lands, coordinate amplification across:

**Owned channels:**
- Organization website / newsroom (link or embed the coverage)
- Email newsletter (feature top placements)
- Internal communications (share wins with leadership and relevant teams)
- Intranet or employee channels

**Shared channels:**
- Organization social accounts (share coverage with appropriate attribution)
- Spokesperson personal social accounts (LinkedIn, X/Twitter)
- Partner or stakeholder social accounts (coordinate if applicable)

**Amplification sequencing:**
- Share coverage within 2-4 hours of publication where possible (freshness matters for social)
- Prioritize amplification of Tier A placements
- Do not share negative coverage on owned/shared channels; handle separately

---

## Post-Campaign Analysis

After the coverage window closes (typically 5-10 business days after release), produce a post-campaign analysis:

1. **Coverage summary**: What ran, where, when
2. **Quantified outcomes**: All metrics above
3. **Key message performance**: Which messages landed, which were missed or misrepresented
4. **Journalist response analysis**: Who engaged, who didn't, any relationship insights
5. **What worked**: Pitches, angles, or timing that drove coverage
6. **What didn't work**: Pitches that failed, journalists who passed, angles that didn't land
7. **Recommendations for next campaign**: Specific changes to targeting, messaging, or timing

---

## Python Integration Note
This skill connects to `scripts/coverage_tracker.py` which can:
- Accept a list of URLs and outlet names
- Pull estimated reach data via NewsAPI
- Calculate quantified reach and sentiment scores automatically
- Output a formatted coverage report as a CSV or Word document

Trigger with: `/pr:coverage-tracker` and provide coverage URLs or outlet names.
