# Transcript — skill engineers-site-observation-report [en] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:09:37+00:00
- duration_s: 28.0
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

Before I draft, I need a few items confirmed. The notes aren't in the five-field format, and splitting them myself would mean deciding where location, observation, and size begin and end. That would risk altering your text.

Time-sensitive flag

The principal's question needs an answer before next week, so this should reach the engineer of record now, not after the report is finalized. I can't answer the principal's question. Whether these conditions are structural or affect safety must be determined by the engineer of record after evaluation. The draft will raise these questions for the engineer of record:

  - Items 1, 2, 4, and 5 all appear to relate to bay 3 or roof drainage. Ponding, a visibly sagging joist (J-14), a missing drain strainer with debris, and stained tiles below bay 3 may be related. Do these items, individually or together, require prompt evaluation or interim precautions before the tournament?
  - Is J-14 located at or near bay 3? Your notes don't say.

Please confirm or correct the following

1. Five-field split. Here is my proposed version. Reply "confirmed" or give corrections. I will copy whatever you approve character-for-character.

   No. | location/grid | observation | approx. size | photo No.
   1 | Roof at bay 3 | ponding after rain; membrane blistering | approx. 10 ft x 6 ft | Photo 11
   2 | Steel joist J-14 bottom chord | visible sag, judged by eye only, not measured | [NOT PROVIDED] | Photo 12
   3 | North masonry wall | stair-step crack | approx. 7 ft long, up to 1/8 in wide (tape) | Photo 13
   4 | Roof drain RD-2 | strainer missing, debris in the bowl | [NOT PROVIDED] | Photo 14
   5 | Ceiling below bay 3 | Ceiling tiles stained | approx. 4 tiles | Photo 15

   Questions on the split:
   - Item 1: does "approx. 10 ft x 6 ft" apply to the ponding only, not the blistering?
   - Item 5: is "approx. 4 tiles" the size, and is "Ceiling below bay 3" acceptable as the location? If not, give the wording you want.
   - Do any items have grid lines you can add?

2. Scope. You described a visual walk-through with no testing. Tape measurement applies to Item 3 only. Can the report state "visual observation only, with tape measurement where noted, no testing or destructive investigation"?

3. Missing inputs. Provide these, or tell me to mark them [NOT PROVIDED]:
   - Attendees' roles
   - Purpose of the visit (for example, a reported leak or cracking)
   - Areas visited. You said "from the floor and the roof." Were any other spaces visited?
   - Areas not visited or inaccessible
   - Project identifier beyond "Example Elementary School gymnasium (fictional)"
   - Visit date: Oct 16, 2026, as given

Once you reply, I'll return the full draft with the DRAFT watermark.

