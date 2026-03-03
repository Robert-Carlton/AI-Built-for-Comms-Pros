# PR Style Guide Skill

## Purpose
Ensure all press release drafts and revisions conform to the organization's established writing style, as documented in the extracted style guide and exemplified by historical releases.

---

## When This Skill Activates
Load this skill automatically whenever:
- Drafting a new press release
- Reviewing or revising an existing press release
- The `/pr:review-release` command is triggered
- The `/pr:extract-style` command is triggered
- Any output includes press release body copy

---

## Style Authority Hierarchy

Apply style guidance in this priority order:

1. **`examples/style-guide-extracted.md`** — The primary authority. This is the explicit, human-reviewed style guide derived from the organization's historical releases. Treat every rule in this document as a hard constraint, not a suggestion.

2. **`examples/releases/`** — The source library. When the extracted guide doesn't address a specific situation, consult the closest analogous example release for reference. Match the pattern observed there.

3. **`skills/pr-release-review.md`** — The structural framework. Ensures all required elements are present even when not addressed by the org style guide.

4. **General AP Style** — Default fallback for anything not covered by the above.

If any conflict exists between these sources, the extracted style guide wins. Flag the conflict to the user if it's significant.

---

## How to Apply the Style Guide

When drafting press release content:

### Step 1: Load the Style Guide
Read `examples/style-guide-extracted.md` before writing any copy. Internalize the documented patterns for:
- Headline construction
- Lead paragraph structure
- Body paragraph cadence
- Data presentation format
- Quote integration and attribution style
- Vocabulary preferences and avoidances
- Tone markers
- Structural norms (paragraph count, ordering)

### Step 2: Draft in Style
Write the draft applying all extracted patterns. Do not default to generic press release conventions if the org style differs.

### Step 3: Self-Check Before Delivering
Before presenting any draft, verify:
- [ ] Headline matches the documented headline pattern (length, voice, structure)
- [ ] Lead paragraph matches the documented lead pattern
- [ ] Statistics are presented in the documented format (rounding, attribution, comparison period)
- [ ] Quotes are introduced and attributed in the documented style
- [ ] Vocabulary avoidances are respected
- [ ] Paragraph count and ordering matches the documented norm
- [ ] Tone matches the documented tone markers
- [ ] Overall, this release would not look out of place alongside the example releases

### Step 4: Flag Style Deviations
If the content of a specific announcement requires deviating from the established style (e.g., an unusual announcement type not represented in the examples), note the deviation explicitly and explain why it was necessary. Do not deviate silently.

---

## If No Style Guide Exists Yet

If `examples/style-guide-extracted.md` does not exist or is empty:
1. Notify the user: "No style guide found yet. Run `/pr:learn-style` and upload 5–10 historical press releases — Claude will convert them, extract your style, and generate both a style guide and a ready-to-use template in one step. No file prep needed."
2. Offer to proceed with general AP style as a temporary fallback.
3. Do not begin a full draft until the user either confirms they want AP style defaults or runs `/pr:learn-style`.

---

## Style Guide Maintenance

The extracted style guide is a living document:
- Re-run `/pr:learn-style` when 5+ new releases have been added to the library
- Human review is required after every extraction — Claude extracts patterns, humans make judgment calls
- Mark manually edited sections with `[MANUALLY EDITED]` so future runs of `/pr:learn-style` do not overwrite intentional human decisions
- The guide is versioned with a date at the top — check the date before using it for a major release
