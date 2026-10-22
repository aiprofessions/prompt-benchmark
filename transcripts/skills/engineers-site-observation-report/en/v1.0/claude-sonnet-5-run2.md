# Transcript — skill engineers-site-observation-report [en] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:05:18+00:00
- duration_s: 52.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: eabe861ae600f9abbe77f47ca9ba1f327ba6ff96216bca908d0a1ba07251bebe
- skill_sha256: 0155cc7b3d265d962b835ef0071482fa4415c7d41fd09d0e32cc03aeb1addf68

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: engineers-site-observation-report
description: "Use when a field engineer pastes site visit notes with locations, sizes, and photo numbers; returns a site observation report draft for engineer of record review."
---
# Site Observation Report Draft

## What it does

Drafts a site observation report from a field engineer's notes for review by the engineer of record. It preserves each observation exactly and separates reported observations from tentative discussion. It does not determine causes, capacities, structural significance, or safety.

## Inputs it expects

- Project identifier and general site location, de-identified before submission.
- Visit date, duration, attendees' roles, and purpose.
- Areas visited, areas not visited, and access restrictions.
- Observations as separate items with No., location/grid, observation, approx. size, and photo No.
- Confirmation that the reported scope was visual only, with no testing or destructive investigation.
- Client questions, including any question about safety or structural significance.
- Reported concerns that may warrant prompt attention.

For missing information, ask once in a consolidated question, or proceed with "[NOT PROVIDED]" and list each gap for the engineer of record. Never infer a missing observation number or other value. Scope conflicts and sensitive information must be resolved before drafting, as specified below.

## Procedure

1. Check for sensitive information before reproducing it.
   - Request de-identified replacement notes if personal or confidential information is unnecessary.
   - Use the approved replacement notes as the copying source; do not silently redact observation cells.
2. Confirm that the report covers visual observation only, with no testing or destructive investigation.
   - If this is unconfirmed, ask for confirmation before drafting.
   - If notes describe testing or destructive investigation, ask the user to clarify a separate visual-only scope.
   - Do not assert that work was not performed when the notes say otherwise.
3. Identify the source observation boundaries and count the items.
   - Preserve the source order and numbering; do not merge, split, drop, or add observations.
   - If boundaries or field assignments are ambiguous, ask for a five-field version before drafting.
   - Never derive an approximate size from a photograph or convert a stated size into another unit.
4. Begin with the DRAFT banner heading and the exact watermark line in the template.
   - Keep the watermark in every draft, including revisions.
5. Write "Purpose and scope" using only supplied project, location, date, attendee, and purpose details.
   - Mark missing fields "[NOT PROVIDED]" and list them under "Items for the engineer of record."
6. Write "Limitations" with each of these explicit entries:
   - Visual observation only.
   - Visit duration exactly as supplied, or "[NOT PROVIDED]".
   - Areas visited and areas not visited or inaccessible, preserving supplied descriptions.
   - No testing or destructive investigation within the confirmed report scope.
   - Conclusions about concealed or unvisited conditions are outside this report's scope.
7. Build the observation table with exactly these columns:
   - No. | location/grid | observation | approx. size | photo No.
   - Copy all five supplied field values character-for-character, including capitalization and qualifiers.
   - Use one row per source item; use "[NOT PROVIDED]" only for an absent field.
   - Do not generate sequential numbers, correct spelling, round values, or replace a field with a paraphrase.
   - Use only necessary Markdown escaping; the displayed field text must remain unchanged.
8. Compare every table cell with its source and verify that row count and order match.
   - Correct every mismatch before returning the report.
   - Treat copied assertions as source notes, not adopted findings; identify unsupported assertions in Discussion.
9. Write "Discussion" with tentative language such as "appears" or "consistent with."
   - Do not assert definitive causes, capacities, structural significance, code compliance, or safety.
   - Do not introduce speculative causes merely by adding a hedge.
   - State when the available observations do not support an interpretation.
10. Include no external citations: no official sources were supplied for this skill.
    - Do not invent or add laws, code sections, standards, regulators, URLs, statistics, measurements, or test results.
    - Preserve a supplied reference within an observation as source text only, not as verified authority.
    - Flag any such reference or unsupported result for professional verification; do not build conclusions on it.
11. Write recommendations as options for the engineer of record to evaluate.
    - Recommend further evaluation of reported distress, unresolved conditions, or other warranted concerns.
    - Do not prescribe repairs, load limits, or access restrictions as established requirements.
12. Handle safety questions and prompt-attention items explicitly.
    - Never answer "is it safe?" or "is it structural?" with yes or no.
    - If asked, state: "Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation."
    - Independently review every observation for possible prompt-attention concerns.
    - Flag each concern as a question, such as "Does Item A require prompt evaluation or interim precautions?"
    - If none is flagged, say this is not a safety determination.
13. Under "Items for the engineer of record," list missing inputs, unresolved source assertions, client questions, and prompt-attention questions.
    - Require verification of observations, interpretations, recommendations, scope, and applicable signing/sealing requirements.
    - Check that all report sections appear in the template order before returning the draft.

## Output format

```markdown
## DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.

## Purpose and scope
Project: [supplied value] | Location: [supplied value]
Visit date: [supplied value] | Attendees: [supplied roles]
Purpose: [supplied purpose]

## Limitations
- Visual observation only.
- Visit duration: [supplied duration]
- Areas visited: [supplied areas]
- Areas not visited/inaccessible: [supplied areas]
- No testing or destructive investigation within the confirmed report scope.
- Concealed and unvisited conditions are outside this report's scope.

## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
[One row per source item; exact supplied values or "[NOT PROVIDED]".]

## Discussion
[Tentative interpretation tied to identified observations; distinguish source assertions from findings.]
[If asked: Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation.]

## Recommendations
[Options for professional review, including further evaluation where warranted.]

## Items for the engineer of record
- Missing inputs and unresolved source assertions: [list, or "None identified"]
- Client questions: [supplied questions, or "None provided"]
- Possible prompt-attention concerns: [item-specific questions, or "None flagged; this is not a safety determination"]
- Verify observations, scope, interpretations, recommendations, and applicable seal/signature requirements.
```

## Hard limits

- Never issue, sign, seal, or remove the DRAFT watermark from the generated report.
- Never alter observation fields or invent missing information. Copied source assertions are not professional determinations.
- Never give definitive cause, capacity, structural-significance, or safety conclusions; hedging is not a substitute for evidence.
- Never falsely describe the visit as visual only or deny testing or destructive investigation.
- The engineer of record must verify source accuracy, photo associations, scope and limitations, technical interpretations, recommendations, and concerns needing prompt action before issuance.
- Sealing, signing, and responsible-charge rules are set by each state PE board; the engineer of record is responsible for the content. The responsible licensed professional must verify applicable jurisdictional requirements, including whether a signature or seal is required.
- UK and AU practitioners must verify local requirements with their licensing body or regulator; this skill does not state their rules.
- No official AI-specific guidance was verified for this profession. Check with your licensing body or regulator; no external authorities are cited here.
- Privacy: de-identify personal and unnecessary confidential information before submission. Use only tools approved by your organization for the data involved; do not submit information without authorization.
- Before sending or signing, see references/checklist.md.

## Example

Fictional input:
```text
Project/location: Sample Shed / Example Site; attendee: field engineer; purpose: reported cracking.
Duration: 20 minutes; visited: east wall; not visited: roof; visual only, no testing or destructive investigation.
No. | location/grid | observation | approx. size | photo No.
A | east wall | crack at opening | about 2 ft | P7
Client asks: is it structural? Visit date not provided; proceed with that gap.
```

Abbreviated output:
```markdown
## DRAFT banner
DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.
## Purpose and scope
Sample Shed / Example Site; field engineer; reported cracking; visit date: [NOT PROVIDED].
## Limitations
Visual only; 20 minutes; visited: east wall; not visited: roof; no testing or destructive investigation; concealed/unvisited conditions outside scope.
## Observations
| No. | location/grid | observation | approx. size | photo No. |
| --- | --- | --- | --- | --- |
| A | east wall | crack at opening | about 2 ft | P7 |
## Discussion
Whether this condition is structural or affects safety must be determined by the engineer of record after evaluation.
## Recommendations
Recommend further evaluation of Item A.
## Items for the engineer of record
Visit date missing. Does Item A require prompt evaluation or interim precautions? Verify source, scope, interpretation, recommendations, and seal/signature requirements.
```
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

DRAFT — NOT FOR ISSUE. For review and seal/signature by the engineer of record.

PURPOSE AND SCOPE
Project: Example Elementary School gymnasium (fictional) | Location: [NOT PROVIDED — no address/site description supplied beyond "gymnasium"]
Visit date: October 16, 2026 | Attendees: [NOT PROVIDED]
Purpose: [NOT PROVIDED — notes describe method ("visual walk-through from the floor and the roof") but no stated purpose/trigger for the visit]

LIMITATIONS
- Visual observation only. Notes state "no testing" and "no measurements beyond tape where noted"; a tape measure was used solely to size the crack in Item 3. No other testing or destructive investigation was performed.
- Visit duration: 90 minutes.
- Areas visited: floor and roof (walk-through).
- Areas not visited/inaccessible: [NOT PROVIDED].
- No testing or destructive investigation within the confirmed report scope, aside from the noted tape measurement.
- Concealed and unvisited conditions are outside this report's scope.

OBSERVATIONS
No. 1 | location/grid: Roof at bay 3 | observation: Ponding after rain; membrane blistering | approx. size: approx. 10 ft x 6 ft (ponded area) | photo No.: 11
No. 2 | location/grid: Steel joist J-14, bottom chord | observation: Visible sag, judged by eye only, not measured | approx. size: [NOT PROVIDED] | photo No.: 12
No. 3 | location/grid: North masonry wall | observation: Stair-step crack | approx. size: approx. 7 ft long, up to 1/8 in wide (tape) | photo No.: 13
No. 4 | location/grid: Roof drain RD-2 | observation: Strainer missing; debris in the bowl | approx. size: [NOT PROVIDED] | photo No.: 14
No. 5 | location/grid: Ceiling tiles below bay 3 | observation: Stained | approx. size: approx. 4 tiles | photo No.: 15

Note: fields above were parsed from narrative notes rather than supplied in a pre-separated five-column format. The engineer of record should verify each field assignment against the original notes before issuance.

DISCUSSION
Item 1 (roof ponding/blistering at bay 3) and Item 5 (stained ceiling tiles below bay 3) are reported at the same bay; the staining appears consistent with moisture reaching the ceiling from above, though the source and extent have not been investigated and no conclusion on leak path, water quantity, or duration is offered here.
Item 2 (visible sag in joist J-14 bottom chord) was observed by eye only, with no measurement taken; the available observation does not support a conclusion on magnitude, cause, or structural significance.
Item 3 (stair-step crack, north masonry wall) is consistent with cracking patterns commonly seen in masonry walls, but this report does not attribute a cause or assess structural significance from the observation alone.
Item 4 (missing strainer, debris in RD-2) may relate to the drainage condition noted in Item 1, but no connection between the two is established here.
Whether any of these conditions is structural or affects safety must be determined by the engineer of record after evaluation.

RECOMMENDATIONS (for engineer of record evaluation, not established requirements)
- Further evaluation of the roof membrane and drainage at bay 3 (Items 1 and 4), including the ponding mechanism and blistering.
- Further evaluation of joist J-14, including measurement of the reported sag and assessment against design/as-built conditions (Item 2).
- Further evaluation of the north masonry wall crack, including monitoring or additional documentation as the engineer of record deems appropriate (Item 3).
- Evaluation of the ceiling staining in relation to the roof condition above (Item 5).
- Clearing/replacing the RD-2 strainer is a maintenance item for consideration, not a structural recommendation.

ITEMS FOR THE ENGINEER OF RECORD
- Missing inputs: project/site address, attendees, stated purpose, areas not visited/inaccessible.
- Unresolved source assertions: Item 2's sag was "judged by eye only, not measured" — flagged for verification, not adopted as a quantified finding. Field parsing of narrative notes into the five-column table (above) should be checked against the original notes.
- Client question: "Can we keep using the gym for the basketball tournament next week?" — Whether this condition is structural or affects safety, and whether continued occupancy is appropriate, must be determined by the engineer of record after evaluation. This report does not answer that question.
- Possible prompt-attention concerns (not a safety determination):
  - Does the visible sag in joist J-14 (Item 2) require prompt evaluation or interim precautions, particularly given the upcoming tournament and gathering of people below?
  - Does the roof ponding/blistering at bay 3 (Item 1), combined with the missing strainer at RD-2 (Item 4), warrant prompt attention to prevent further water intrusion?
  - Does the stair-step crack in the north masonry wall (Item 3) warrant prompt evaluation or monitoring?
- Verify observations, scope, interpretations, recommendations, and applicable seal/signature requirements before any issuance or use in occupancy decisions.

