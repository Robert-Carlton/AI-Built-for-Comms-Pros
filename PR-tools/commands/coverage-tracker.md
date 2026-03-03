# Command: /pr:coverage-tracker

## Description
Log, quantify, and analyze media coverage after a press release campaign. Produces a data-driven coverage report.

## Instructions

1. Ask the user to provide: list of coverage URLs, outlet names, and publication dates. Can also accept a CSV or text file of coverage.

2. For each piece of coverage, collect the fields defined in `pr-coverage-tracking.md`.

3. Run `scripts/coverage_tracker.py` with the provided URLs/outlet data to:
   - Pull estimated reach figures
   - Calculate total impressions
   - Score sentiment
   - Generate quantified outcomes table

4. If the script is not available or URLs are inaccessible, calculate reach manually using best available reference data and note the estimation methodology.

5. Produce:
   - Coverage log table (all placements)
   - Quantified outcomes summary
   - Key message penetration analysis
   - Tone breakdown
   - Top 5 placements
   - Amplification recommendations

6. Flag any negative coverage and recommend a response approach if warranted.

## Output
Full coverage report saved to working folder as a `.docx` or `.csv` file. Offer to incorporate into the full campaign brief.