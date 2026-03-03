# Campaign Brief Skill

## Purpose
Compile all work produced across the campaign workflow into a single, structured, professional document that can be shared with clients, leadership, or team members. This is the master deliverable of the plugin.

---

## When to Use
Trigger this skill when:
- A complete campaign brief is needed before outreach begins
- A post-campaign report is needed after coverage tracking is complete
- A progress update is needed mid-campaign

---

## Campaign Brief Structure

Produce the campaign brief as a formatted Word document (`.docx`) using the standard document skill. The brief should contain the following sections:

---

### SECTION 1: Campaign Overview
- **Announcement title / working headline**
- **Organization**: Who is making the announcement
- **Release date / embargo date** (if applicable)
- **Campaign objective**: What does success look like? (e.g., 10+ placements, national coverage, specific outlet targets)
- **Primary spokesperson**: Name, title, availability window
- **Campaign manager**: Who owns this

---

### SECTION 2: News Value Assessment
- **Newsworthiness summary**: 2-3 sentences on why this is news
- **Newsworthiness score by dimension**: Timeliness / Magnitude / Novelty / Proximity / Human Interest / Conflict (rate each High / Medium / Low)
- **Overall news value rating**: Strong / Moderate / Weak — with rationale
- **Risks or caveats**: Anything that might undercut news value

---

### SECTION 3: Competitive Positioning
- **Competitive landscape summary**: What comparable announcements exist? How do we compare?
- **Primary USP**: The one thing we can say that no one else can say right now
- **Supporting USPs** (2-3)
- **Proof points** for each USP
- **Positioning statement**: 1-2 sentence version suitable for pitch copy
- **Anticipated journalist objections and responses**

---

### SECTION 4: Press Release Status
- **Release status**: Draft / Approved / Final
- **Key messages confirmed**: List each key message (maximum 3-5)
- **Structural review findings**: Summary of any issues identified and whether resolved
- **Outstanding items**: Anything still needed before release is pitch-ready

---

### SECTION 5: Target Media Strategy
- **Target audience profile**: Who we are trying to reach through coverage
- **Coverage type priorities**: Breaking news / Feature / Trend / Podcast / Newsletter / etc.
- **Tier A targets** (full list with rationale for each)
- **Tier B targets** (list)
- **Tier C targets** (list or "broad wire distribution")
- **Excluded segments**: Any beats or outlets deliberately excluded and why
- **Relationship notes**: Warm contacts, prior coverage history, notable relationship considerations

---

### SECTION 6: Pitch Strategy
- **Distribution approach**: Exclusive / Embargo / Broad — with rationale
- **Pitch angles by segment**: Which angle for which journalist type
- **Subject line options**: Top 3 recommended subject lines
- **Tier A pitch copy**: Full pitch text for top-tier personalized outreach
- **Tier B pitch copy**: Segment-specific pitch template
- **Tier C pitch copy**: Broad distribution template

---

### SECTION 7: Outreach Execution Plan
- **Sequencing timeline**: Day-by-day outreach schedule
- **Follow-up schedule**: When and how follow-up will be handled
- **Embargo management details** (if applicable)
- **Asset readiness checklist**: Status of all supporting materials

---

### SECTION 8: Coverage Results *(Post-Campaign Only)*
- **Coverage log table**: All placements with full details
- **Quantified outcomes**: Total placements, estimated impressions, reach by tier
- **Key message penetration**: Which messages appeared in coverage, at what rate
- **Tone breakdown**: % positive / neutral / negative
- **Top 5 placements** with brief description of each
- **Amplification actions taken**

---

### SECTION 9: Post-Campaign Analysis *(Post-Campaign Only)*
- **What worked**: Specific pitches, angles, timing, or journalist relationships that drove coverage
- **What didn't work**: What failed and why
- **Journalist relationship updates**: New warm contacts, relationships damaged, notable responses
- **Recommendations for next campaign**: Specific, actionable improvements

---

### SECTION 10: Appendices
- Full press release text
- Complete media list (all tiers, with contact info)
- All pitch copy versions
- Supporting data or research

---

## Formatting Standards
- Professional document with clear section headers
- Tables for media list, coverage log, and metrics
- Executive summary on page 1 (3-5 sentences covering objective, strategy, and key outcomes)
- Page numbers and date on all pages
- Produced as a `.docx` file for easy editing and sharing

---

## Output
When `/pr:campaign-brief` is triggered:
1. Ask the user: "Is this a pre-campaign brief, mid-campaign update, or post-campaign report?"
2. Load only the sections relevant to the campaign stage
3. Pull from all previously generated work in the session (competitive analysis, media list, pitches, coverage data)
4. Produce the complete document and save to the working folder
5. Present a summary of what's included and note any sections that require additional information to complete