# Transcript — skill engineers-site-observation-report [en] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:26:46+00:00
- duration_s: 67.4
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

DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.

Purpose and scope
Project: Example Elementary School gymnasium (fictional) | Location: [NOT PROVIDED] (general site location beyond the project name not stated)
Visit date: Oct 16, 2026 | Attendees: field engineer (author of notes); other attendees: [NOT PROVIDED] | Purpose: [NOT PROVIDED]
Scope: visual-observation draft; testing and destructive-investigation interpretation excluded.

Limitations
- Visual-only visit status: visual walk-through from the floor and the roof; no measurements beyond tape where noted (tape used at Item 3 only).
- Visit duration: 90 minutes
- Areas visited: gymnasium floor and roof
- Areas not visited/inaccessible: [NOT PROVIDED]
- Testing: none (notes state "no testing")
- Destructive investigation: [NOT PROVIDED]
- Concealed and unvisited conditions are outside this report's scope.

Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
| 1 | Roof at bay 3 | ponding approx. 10 ft x 6 ft after rain; membrane blistering | approx. 10 ft x 6 ft | Photo 11 |
| 2 | Steel joist J-14 bottom chord | visible sag, judged by eye only, not measured | [NOT PROVIDED] (not measured) | Photo 12 |
| 3 | North masonry wall | stair-step crack approx. 7 ft long, up to 1/8 in wide (tape) | approx. 7 ft long, up to 1/8 in wide (tape) | Photo 13 |
| 4 | Roof drain RD-2 | strainer missing, debris in the bowl | [NOT PROVIDED] | Photo 14 |
| 5 | below bay 3 | Ceiling tiles stained below bay 3, approx. 4 tiles | approx. 4 tiles | Photo 15 |

Source items counted: 5. Table rows: 5, in source order. Field assignment (location/observation/size) was separated by the drafter from running text; see Items for the engineer of record.

Discussion
- Items 1, 4, and 5 are all water-related notes. Item 1 (ponding and membrane blistering at bay 3) and Item 5 (stained ceiling tiles below bay 3) are at the same bay and appear consistent with water reaching the ceiling in that area. The notes do not state whether drain RD-2 (Item 4) serves bay 3, so the observations do not support linking the missing strainer to the ponding.
- Item 2 records a visible sag at the J-14 bottom chord, judged by eye and not measured. The magnitude of the sag, whether it is within normal tolerance, and whether it is related to the ponding at bay 3 are not established by the observations. Note: the record does not state whether J-14 is at or near bay 3.
- Item 3 is a stair-step crack with tape-measured length and width. The observations do not support an interpretation of cause, age, or activity (no prior survey or crack monitoring is noted).
- All entries are source notes from a visual walk-through, not adopted findings.
- Regarding the principal's question: Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation. This draft does not answer whether the gymnasium can be used for the tournament.

Recommendations (options for the engineer of record to evaluate)
- Further evaluation of Item 2 (J-14 sag), including measurement of the deflection and review of the joist's relationship to the bay 3 ponding area.
- Further evaluation of Item 1 ponding (extent, depth, duration, relation to roof slope and drainage) and of the membrane blistering.
- Further evaluation of Item 3, including crack mapping and consideration of crack monitoring to establish whether the crack is active.
- Review of Item 4 (RD-2 strainer missing, debris) in relation to roof drainage performance; which bays RD-2 serves should be confirmed.
- Review of Item 5 in conjunction with Item 1 to confirm whether the staining corresponds to active leakage.
- Consider whether a response to the principal's tournament question is needed before the event date, and what evaluation is required to support it.
No repairs, load limits, or access restrictions are prescribed here.

Items for the engineer of record
- Missing inputs, ambiguities, scope conflicts, unsupported assertions:
  - Purpose of visit: [NOT PROVIDED].
  - General site location: [NOT PROVIDED].
  - Other attendees and their roles: [NOT PROVIDED].
  - Areas not visited or inaccessible: [NOT PROVIDED] (e.g., above-ceiling space, roof framing other than J-14).
  - Destructive investigation status: not stated; "no testing" was stated.
  - Field assignment: the drafter separated location, observation, and approx. size from running text for Items 1–5; verify the splits, especially Item 5 location ("below bay 3") and whether "Roof at bay 3" is a grid reference.
  - Item 2: "visible sag, judged by eye only" is an unmeasured source note; not a finding of deflection.
  - Item 1: "after rain" — time since rainfall and ponding depth not recorded.
  - Item 4: which roof area RD-2 drains is not recorded.
  - Relationship between J-14 and bay 3 is not recorded.
  - Confirm photo associations (Photos 11–15) against the camera record.
  - Notes contain no personal names; the fictional school name is retained as supplied.
- Client questions:
  - Principal (role): "Can we keep using the gym for the basketball tournament next week?" — not answered in this draft; requires determination by the engineer of record. Tournament timing creates a decision deadline.
- Possible prompt-attention concerns:
  - Does Item 2 (J-14 bottom chord sag) require prompt evaluation or interim precautions?
  - Does Item 1 (ponding at bay 3, with Item 5 staining below) require prompt evaluation or interim precautions, including before further rainfall?
  - Does Item 3 (stair-step crack, north masonry wall) require prompt evaluation or interim precautions?
  - Does the combination of Items 1, 2, and 5 at or near bay 3 require prompt evaluation before the tournament?
  - These are questions, not safety determinations.
- Verify observations, scope, interpretations, recommendations, and seal/signature requirements before issuance.

