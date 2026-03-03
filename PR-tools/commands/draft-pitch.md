# Command: /pr:draft-pitch

## Description
Write personalized pitch emails for each journalist tier and angle segment.

## Instructions

1. Confirm the following inputs are available (ask if not):
   - Approved or near-final press release
   - Completed media list with tiers
   - Competitive positioning statement and USPs
   - Spokesperson availability window
   - Distribution strategy (exclusive / embargo / broad)

2. Apply the pitch drafting framework from `pr-pitch-drafting.md`.

3. Produce pitches segmented by:
   - Tier (A / B / C)
   - Angle (business press / consumer press / trade / local / broadcast / podcast)

4. For each Tier A journalist on the list, produce a genuinely personalized pitch that references their specific recent work.

5. Run `scripts/pitch_analyzer.py` on each draft to score quality and flag issues before delivering.

6. Present all pitches with subject line options and strategic rationale.

## Output
Complete set of pitch drafts, organized by tier and segment. Save to working folder. Offer to proceed to outreach execution planning or subject line optimization.