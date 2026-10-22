# Transcript — skill engineers-site-observation-report [en] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:41:59+00:00
- duration_s: 44.5
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
Visit date: Oct 16, 2026 | Attendees: field engineer (author of notes); other attendees' roles [NOT PROVIDED] | Purpose: [NOT PROVIDED]
Scope: visual-observation draft; testing and destructive-investigation interpretation excluded.

## Limitations
- Visual-only visit status: Visual walk-through from the floor and the roof; no measurements beyond tape where noted.
- Visit duration: 90 minutes
- Areas visited: gymnasium, from the floor and the roof
- Areas not visited/inaccessible: [NOT PROVIDED]
- Testing: no testing (as stated in notes)
- Destructive investigation: [NOT PROVIDED]
- Item 2 (joist sag) was judged by eye only and was not measured. Item 3 dimensions were taken by tape. No other measurements are reported.
- Concealed and unvisited conditions are outside this report's scope.

## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
| 1 | Roof at bay 3 | ponding approx. 10 ft x 6 ft after rain; membrane blistering | approx. 10 ft x 6 ft | Photo 11 |
| 2 | Steel joist J-14 bottom chord | visible sag, judged by eye only, not measured | [NOT PROVIDED] | Photo 12 |
| 3 | North masonry wall | stair-step crack approx. 7 ft long, up to 1/8 in wide (tape) | approx. 7 ft long, up to 1/8 in wide (tape) | Photo 13 |
| 4 | Roof drain RD-2 | strainer missing, debris in the bowl | [NOT PROVIDED] | Photo 14 |
| 5 | below bay 3 | Ceiling tiles stained below bay 3, approx. 4 tiles | approx. 4 tiles | Photo 15 |

Note: For Items 1, 3, and 5, the full source text is kept unchanged in the observation cell. The size values were also copied into the size column. See the items for the engineer of record below.

## Discussion
- Items 1 and 5 are both reported at bay 3: roof ponding and membrane blistering above, and stained ceiling tiles below. The co-location is consistent with water reaching the interior near bay 3. The notes do not establish a leak path, how long it has been active, or whether the staining is current.
- Item 4 records a missing strainer and debris in the bowl at RD-2. The notes do not say where RD-2 is relative to bay 3. They also do not establish whether RD-2's condition relates to the ponding in Item 1. No connection is adopted here.
- Item 2 records a visible sag in the J-14 bottom chord. It was judged by eye only. Without a measurement or a reference line, the observation does not support conclusions about magnitude, cause, or capacity. The notes do not say whether J-14 is in or near bay 3. If it is, the engineer of record may wish to evaluate Items 1 and 2 together.
- Item 3 records a stair-step crack in the north masonry wall, with tape dimensions. The notes do not establish cause, age, activity, or significance.
- The principal asked: "Can we keep using the gym for the basketball tournament next week?" Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation. This draft does not answer whether continued use is appropriate.

## Recommendations
These are options for the engineer of record to evaluate:
- Evaluate the observed conditions before the planned tournament next week, given the principal's question and timing.
- Measure the J-14 bottom-chord deflection and check adjacent joists, if the engineer of record considers it warranted.
- Locate J-14 and RD-2 relative to bay 3. Assess whether the conditions are related.
- Have the roof membrane, ponding area, and drainage at bay 3 and RD-2 evaluated. This could include reviewing other roof drains not described in the notes.
- Investigate the source of the ceiling-tile staining below bay 3. Check whether moisture is active.
- Evaluate the north wall crack. Consider whether documentation or monitoring is warranted.
- Decide whether any interim precautions are warranted pending evaluation. This draft does not establish any as requirements.

## Items for the engineer of record
- Missing inputs, ambiguities, scope conflicts, unsupported assertions:
  - Site location, visit purpose, and other attendees' roles: [NOT PROVIDED].
  - Destructive investigation status: [NOT PROVIDED].
  - Areas not visited or inaccessible: [NOT PROVIDED]. This includes whether the ceiling plenum or joist top chords were accessible.
  - Was J-14 viewed from the floor, the roof, or both?
  - Item 1: does "approx. 10 ft x 6 ft" apply to the ponding only, or also to the blistering? How long after rain was the ponding observed?
  - Item 5: is the location "below bay 3" correct as assigned? Does the size "approx. 4 tiles" describe the stained area?
  - Items 1, 3, 5: confirm that copying the size into both the observation and size columns is acceptable.
  - Where are J-14 and RD-2 relative to bay 3?
  - Scope check: the notes say "no testing" but also report tape measurements. Confirm how tape measurements should be characterized.
  - Confirm that each photo number (Photos 11–15) matches the item it is assigned to.
- Client questions:
  - The principal asked: "Can we keep using the gym for the basketball tournament next week?" This requires an evaluation by the engineer of record. The draft does not answer it.
- Possible prompt-attention concerns:
  - Does Item 2 (J-14 visible sag) require prompt evaluation or interim precautions before the tournament?
  - Does Item 1 (ponding and blistering at bay 3) require prompt evaluation or interim precautions, especially if more rain is expected?
  - Does Item 4 (RD-2 strainer missing, debris in bowl) require prompt attention to roof drainage?
  - Does Item 5 (stained tiles below bay 3) require prompt evaluation for active leaking or tile condition over the playing area?
  - Does Item 3 (north wall stair-step crack) require prompt evaluation or interim precautions?
- Verify observations, scope, interpretations, recommendations, and seal/signature requirements before issuance. Sealing and signing rules are set by the applicable licensing board.

