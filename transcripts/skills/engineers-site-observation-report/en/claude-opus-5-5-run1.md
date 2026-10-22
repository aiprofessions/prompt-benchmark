# Transcript — skill engineers-site-observation-report [en] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:31:24+00:00
- duration_s: 42.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: eabe861ae600f9abbe77f47ca9ba1f327ba6ff96216bca908d0a1ba07251bebe
- skill_sha256: 5d694f4bf02dbc94ef85f7c941718a44a3cee96e779393289ee1644a4ddde235

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: engineers-site-observation-report
description: "Use when a field engineer pastes site visit notes with locations, sizes, and photo numbers; returns a site observation report draft for engineer of record review."
---
# Site Observation Report Draft

## What it does

Drafts a site observation report from field notes for review by the engineer of record. It preserves observation entries exactly and separates source notes from tentative discussion. It delivers the complete draft in one reply, with unresolved questions at the end. It does not determine causes, capacities, structural significance, or safety.

## Inputs it expects

- Project identifier and general site location, de-identified before submission.
- Visit date, duration, attendees' roles, and purpose.
- Areas visited, areas not visited, and access restrictions.
- Separate observations with No., location/grid, observation, approx. size, and photo No.
- Whether the visit was visual only and whether testing or destructive investigation occurred.
- Client questions, including questions about safety or structural significance.
- Reported concerns that may warrant prompt attention.

For missing or ambiguous information, proceed with "[NOT PROVIDED]" and collect questions in the final section. Do not guess site facts, observation values, visit methods, or results.

## Procedure

1. Produce the complete report in the first reply.
   - Include all seven output sections, the DRAFT watermark, and the observation table.
   - Never stop for clarification, promise a later draft, or withhold a section pending answers.
   - Use "[NOT PROVIDED]" for missing information; do not assume facts about the visit.
   - Collect every unresolved question under "Items for the engineer of record."
2. Apply privacy controls.
   - Outside copied observation fields, identify people by role rather than name.
   - Do not enrich identifiers or repeat confidential details elsewhere in the report.
   - If sensitive details remain in observation fields, preserve source fidelity but flag the need for a de-identified source before circulation.
3. Establish the scope from the supplied notes.
   - Identify this deliverable as a visual-observation draft, not a testing or destructive-investigation report.
   - Record whether the actual visit was visual only; if unstated, write "Visual-only visit status: [NOT PROVIDED]."
   - State "No testing or destructive investigation" only when the notes establish both.
   - Otherwise mark each unknown status "[NOT PROVIDED]"; if either activity occurred, record that fact without denying it or inventing results.
   - Refer testing-related interpretation and any scope conflict to the engineer of record.
4. Identify and count source observation items before drafting.
   - Preserve their order and numbering; do not merge, split, drop, or add items.
   - If an item's fields are ambiguous, retain its unassignable text unchanged in the observation cell.
   - Copy clearly assigned fields exactly; mark unresolved fields "[NOT PROVIDED]" and list the assignment question.
   - If no observations were supplied, retain the table header without inventing a data row and list the missing observations.
5. Begin with the DRAFT banner heading and the exact watermark line in the template.
   - Retain the watermark in every generated draft and revision.
6. Write "Purpose and scope" from supplied project, location, date, role, and purpose details.
   - Mark missing details "[NOT PROVIDED]" and state the visual-observation scope.
7. Write "Limitations" with each of these explicit entries:
   - Visual-only visit status, as supplied or "[NOT PROVIDED]".
   - Visit duration exactly as supplied, or "[NOT PROVIDED]".
   - Areas visited and areas not visited or inaccessible, preserving supplied descriptions or marking gaps.
   - Testing status and destructive-investigation status, separately if needed, following Step 3.
   - Concealed and unvisited conditions are outside this report's scope.
8. Build the observation table with these exact columns:
   - No. | location/grid | observation | approx. size | photo No.
   - Copy all supplied field values character-for-character, preserving capitalization, qualifiers, and units.
   - Use one row per source item and "[NOT PROVIDED]" for missing or unresolved fields.
   - Do not generate numbering, correct spelling, paraphrase, round, convert units, or estimate sizes from photographs.
   - Use only necessary Markdown escaping; do not change the underlying field text.
9. Check every table cell against its source and correct copying errors.
   - Verify that row count and order match the source items.
   - Treat copied assertions as source notes, not adopted findings; flag unsupported assertions in Discussion.
10. Write "Discussion" using tentative language such as "appears" or "consistent with" only where supported.
    - Do not assert definitive causes, capacities, structural significance, code compliance, or safety.
    - Do not introduce speculative causes merely by adding a hedge.
    - State when the observations do not support an interpretation.
11. Add no external citations; no official sources were supplied.
    - Do not invent laws, code sections, standards, regulators, dates, URLs, statistics, measurements, or test results.
    - A reference already inside an observation must remain exact as source text, not an endorsed citation.
    - Flag such references for professional verification; do not repeat them as authorities or base conclusions on them.
12. Write recommendations as options for the engineer of record to evaluate.
    - Recommend further evaluation where reported distress, unresolved conditions, or other concerns warrant it.
    - Do not prescribe repairs, load limits, or access restrictions as established requirements.
13. Address safety questions and possible prompt-attention items.
    - Never answer "is it safe?" or "is it structural?" with yes or no.
    - If asked, state: "Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation."
    - Review each observation for possible prompt-attention concerns and flag each concern as a question.
    - Use wording such as "Does Item A require prompt evaluation or interim precautions?"
    - If none is flagged, state that this is not a safety determination.
14. Complete "Items for the engineer of record" and perform a final check.
    - List missing inputs, field ambiguities, scope conflicts, unsupported assertions, client questions, and prompt-attention questions.
    - Require verification of observations, scope, interpretations, recommendations, and signing/sealing requirements.
    - Confirm that all seven sections appear in template order and no questions were used to delay the draft.

## Output format

```markdown
## DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.

## Purpose and scope
Project: [value] | Location: [value]
Visit date: [value] | Attendees: [roles] | Purpose: [value]
Scope: visual-observation draft; testing and destructive-investigation interpretation excluded.

## Limitations
- Visual-only visit status: [supplied status or NOT PROVIDED]
- Visit duration: [supplied duration or NOT PROVIDED]
- Areas visited: [value or NOT PROVIDED]
- Areas not visited/inaccessible: [value or NOT PROVIDED]
- Testing: [none, if established; otherwise supplied status or NOT PROVIDED]
- Destructive investigation: [none, if established; otherwise supplied status or NOT PROVIDED]
- Concealed and unvisited conditions are outside this report's scope.

## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
[One row per source item; exact supplied values or "[NOT PROVIDED]".]

## Discussion
[Supported tentative interpretation; distinguish source assertions from findings.]
[If asked: Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation.]

## Recommendations
[Options for professional review, including further evaluation where warranted.]

## Items for the engineer of record
- Missing inputs, ambiguities, scope conflicts, unsupported assertions: [list or "None identified"]
- Client questions: [list or "None provided"]
- Possible prompt-attention concerns: [questions or "None flagged; this is not a safety determination"]
- Verify observations, scope, interpretations, recommendations, and seal/signature requirements.
```

Replace missing-value placeholders with the literal "[NOT PROVIDED]"; do not leave instructional template text in the report.

## Hard limits

- Never issue, sign, seal, or remove the DRAFT watermark from a generated report.
- Never alter supplied observation values or invent missing information; source assertions are not professional determinations.
- Never give definitive cause, capacity, structural-significance, or safety conclusions; hedging does not supply evidence.
- Never assume visual-only methods or the absence of testing; never deny activities described in the notes.
- The engineer of record must verify source accuracy, photo associations, missing information, scope and limitations, interpretations, recommendations, and concerns needing prompt action before issuance.
- Sealing, signing, and responsible-charge rules are set by each state PE board; the engineer of record is responsible for the content. The responsible licensed professional must verify applicable requirements, including whether a signature or seal is required.
- UK and AU practitioners must verify local requirements with their licensing body or regulator; this skill does not state their rules.
- No official AI-specific guidance was verified for this profession. Check with your licensing body or regulator; no external authorities are cited here.
- Privacy: de-identify personal and unnecessary confidential information before submission. Use only tools approved by your organization for the data involved. Do not circulate a draft containing unnecessary sensitive source details; obtain a de-identified source and regenerate it.
- Before sending or signing, see references/checklist.md.

## Example

Fictional input:
```text
Project/location: Sample Shed / Example Site; attendee: field engineer; purpose: reported cracking.
Duration: 20 minutes; visited: east wall; not visited: roof.
No. | location/grid | observation | approx. size | photo No.
A | east wall | crack at opening | about 2 ft | P7
Client asks: is it structural?
```

Abbreviated output:
```markdown
## DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.
## Purpose and scope
Sample Shed / Example Site; field engineer; reported cracking; visit date: [NOT PROVIDED]; visual-observation draft only.
## Limitations
Visual-only visit status: [NOT PROVIDED]; testing: [NOT PROVIDED]; destructive investigation: [NOT PROVIDED]; duration: 20 minutes; visited: east wall; not visited: roof; concealed/unvisited conditions excluded.
## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
| A | east wall | crack at opening | about 2 ft | P7 |
## Discussion
The note does not establish significance. Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation.
## Recommendations
Recommend further evaluation of Item A.
## Items for the engineer of record
```
Final-section entry: What were the visit date and actual investigation methods? Does Item A require prompt evaluation or interim precautions? Verify source, scope, interpretation, recommendations, and seal/signature requirements.
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Draft the site observation report from my notes.
Visit: Example Elementary School gymnasium (fictional), Oct 16, 2026. Visual walk-through from the floor and the roof, 90 minutes, no testing, no measurements beyond tape where noted.
1. Roof at bay 3: ponding approx. 10 ft x 6 ft after rain; membrane blistering. Photo 11.
2. Steel joist J-14 bottom chord: visible sag, judged by eye only, not measured. Photo 12.
3. North masonry wall: stair-step crack approx. 7 ft long, up to 1/8 in wide (tape). Photo 13.
4. Roof drain RD-2: strainer missing, debris in the bowl. Photo 14.
5. Ceiling tiles stained below bay 3, approx. 4 tiles. Photo 15.
The principal asked: "Can we keep using the gym for the basketball tournament next week?"
````

## Output (verbatim stdout, session metadata stripped)

## DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.

## Purpose and scope
Project: Example Elementary School gymnasium (fictional) | Location: [NOT PROVIDED]
Visit date: Oct 16, 2026 | Attendees: [NOT PROVIDED] | Purpose: [NOT PROVIDED]
Scope: visual-observation draft; testing and destructive-investigation interpretation excluded.

## Limitations
- Visual-only visit status: Visual walk-through from the floor and the roof; no measurements beyond tape where noted
- Visit duration: 90 minutes
- Areas visited: from the floor and the roof
- Areas not visited/inaccessible: [NOT PROVIDED]
- Testing: None ("no testing")
- Destructive investigation: [NOT PROVIDED]
- Concealed and unvisited conditions are outside this report's scope.

## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
| 1 | Roof at bay 3 | ponding approx. 10 ft x 6 ft after rain; membrane blistering | approx. 10 ft x 6 ft | Photo 11 |
| 2 | Steel joist J-14 bottom chord | visible sag, judged by eye only, not measured | [NOT PROVIDED] | Photo 12 |
| 3 | North masonry wall | stair-step crack approx. 7 ft long, up to 1/8 in wide (tape) | approx. 7 ft long, up to 1/8 in wide (tape) | Photo 13 |
| 4 | Roof drain RD-2 | strainer missing, debris in the bowl | [NOT PROVIDED] | Photo 14 |
| 5 | below bay 3 | Ceiling tiles stained below bay 3, approx. 4 tiles | approx. 4 tiles | Photo 15 |

## Discussion
The table entries are field notes, not adopted findings.

Item 1 records ponding at bay 3 after rain, with membrane blistering. The notes do not give ponding depth or the extent of the blistering.

Item 5 records stained ceiling tiles below bay 3. The stains appear consistent with water reaching the interior near the area of Item 1. The notes do not establish an active leak, the water source, or when the staining occurred.

Item 4 records a missing strainer and debris at roof drain RD-2. The notes do not say where RD-2 is relative to bay 3. They also do not show whether RD-2 drains bay 3 or whether its condition is related to the ponding in Item 1.

Item 2 records visible sag at joist J-14's bottom chord. The sag was judged by eye only and was not measured. The notes do not say where J-14 is relative to bay 3. They do not support any conclusion about the magnitude of the deflection, its cause, or any relationship to ponding.

Item 3 records a stair-step crack in the north masonry wall, measured by tape. The notes do not support any conclusion about the crack's cause, whether it is active, or its significance.

The principal asked: "Can we keep using the gym for the basketball tournament next week?" Whether these conditions are structural or affect safety must be determined by the engineer of record after evaluation. This draft does not answer the occupancy question.

## Recommendations
Options for the engineer of record to evaluate:
- Evaluate Items 1, 2, 4, and 5 together, and consider whether to do so before the tournament next week. This includes confirming the locations of J-14 and RD-2 relative to bay 3.
- Consider measuring J-14's deflection, and the depth of ponding at bay 3, if the evaluation warrants it.
- Consider clearing and restoring drainage at RD-2, subject to the engineer of record's evaluation and the owner's maintenance processes.
- Consider evaluating the north wall crack in Item 3, which could include monitoring.
- Consider evaluating the roof membrane at bay 3, including the blistering.
- Decide what response to give the principal about the tournament, and when to give it.

## Items for the engineer of record
- Missing inputs, ambiguities, scope conflicts, unsupported assertions:
  - Missing inputs: site location, attendees' roles, visit purpose, areas not visited or inaccessible, and destructive-investigation status.
  - Item 1: field assignment needs confirmation. The size was copied into the size column and also kept in the observation text. Does "approx. 10 ft x 6 ft" apply only to the ponding? What is the extent of the blistering? What was the ponding depth?
  - Item 1: was the ponding size measured by tape or estimated?
  - Item 2: no size was recorded because the sag was not measured. The bay or grid location of J-14 is not stated.
  - Item 4: the bay or grid location of RD-2 is not stated. Which roof area does RD-2 serve?
  - Item 5: the location field was taken from "below bay 3." Please confirm this assignment. "approx. 4 tiles" is a count, not a dimension; please confirm it belongs in the size column.
  - Items 2 and 4: the source does not include a grid reference.
  - The trailing periods in the source entries were treated as delimiters and omitted from the table cells.
  - Were the photo numbers verified against the photo log?
- Client questions:
  - The principal asked: "Can we keep using the gym for the basketball tournament next week?" This must be answered by the engineer of record after evaluation.
- Possible prompt-attention concerns:
  - Do Items 1, 2, 4, and 5 require prompt evaluation or interim precautions? This includes whether they should be evaluated together, given the reported ponding, unmeasured joist sag, an obstructed drain, and interior staining.
  - Does Item 2 require prompt evaluation or interim precautions before the gym is used next week?
  - Does Item 3 require prompt evaluation or interim precautions?
- Verify observations, scope, interpretations, recommendations, and seal/signature requirements.

