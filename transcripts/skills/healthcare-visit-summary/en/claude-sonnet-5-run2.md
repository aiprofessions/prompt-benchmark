# Transcript — skill healthcare-visit-summary [en] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:36:34+00:00
- duration_s: 39.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e88c591c65d269456b408fbd7e79e5a4f556c220c58d8afcc0acc5c79f8bfdde
- skill_sha256: 2e5ab16f8aaf11a94d38799b519c540a2f7f456787a7875083ea7654e37b2527

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Use when a clinician or nurse pastes a visit note to draft a patient-friendly summary, a clinician-only red-flag check, and a missing-information list."
---

# Patient-Friendly Visit Summary + Red-Flag Check

## What it does

Drafts a patient-friendly after-visit summary from a clinician's or nurse's visit note.
Separately checks for unaddressed concerns, contradictions, and missing follow-up details.
The responsible clinician reviews, resolves questions, and signs before any patient-facing text is shared.

## Inputs it expects

- A de-identified visit note, unless the organization confirms this tool is covered by its agreements and approved for the information.
- The reason for the visit, assessment, and plan as documented.
- Every vital sign, measurement, and lab value, with recorded values and units.
- Medication information, including changes, doses, units, frequency, and timing.
- Allergies and documented reactions.
- Follow-up instructions and the clinician's return or urgent precautions.
- Optional: patient communication needs and practice jurisdiction.

If no visit note is supplied, ask for one before drafting.
For other missing information, ask once in one consolidated message, or proceed with supported content and list every gap under "Missing / to confirm."
Never guess; an absent allergy list does not mean no allergies.
The privacy gate below applies even when the user asks to proceed without clarification.

## Procedure

1. Check privacy before drafting.
   If apparent identifiers are present and organizational approval is unconfirmed, stop and request a de-identified note or confirmation of approved use.
   Do not repeat identifiers in the request; an explicitly fictional case label is not a real patient identifier.
2. Extract the visit reason, findings, plan, medications, allergies, symptoms, concerns, follow-up, and precautions.
   Create an internal inventory of every recorded vital sign, measurement, and lab value, preserving its label, value, unit, and context.
   Record missing or conflicting information; handle clarification as described above.
3. Start every draft with "DRAFT — for clinician review before sharing with the patient."
   Use the output sections below in their stated order.
4. Check instructions for ambiguity or contradictions before putting them in Part A.
   Withhold disputed medication directions, unclear precautions, and other conflicting instructions pending confirmation.
   Quote the relevant source wording in Part B as a question and list the withheld item under "Missing / to confirm."
   Do not choose between conflicting instructions or silently repair a suspected error.
   Conflicting measurements are not withheld: retain them as specified in step 7.
5. Write Part A at approximately a 6th–8th grade reading level.
   Use short sentences, common words, and "you" or "your"; explain medical terms and abbreviations on first use.
   Keep explanations general and nonnumeric, such as "A1c (a blood test that measures average blood sugar)."
   Do not add a diagnosis, prognosis, result interpretation, or clinical instruction through an explanation.
6. Copy every included number, dose, unit, frequency, duration, and follow-up date exactly from the note.
   Do not round, convert, calculate, normalize notation, or insert a missing unit.
   Do not introduce numbers through explanations; explain unfamiliar units separately without replacing the recorded unit.
7. Put every vital sign, measurement, and lab value from the inventory in Part A under "Your measurements and test results."
   Preserve each exact value and unit; omit none, including weight and measurements outside the main findings section.
   Match each inventory item to its Part A entry individually, then verify that the counts match.
   Preserve labels and context needed to distinguish repeated, historical, or conflicting measurements.
   Do not label a value high, low, normal, or improved unless the note says so; copy any such characterization exactly.
   If a unit is absent, copy the value as written, add no unit, and flag the omission in Part B and "Missing / to confirm."
   If values conflict, copy each as written and flag the conflict; do not choose between them.
8. Copy each unambiguous medication change verbatim, including the drug, dose, units, frequency, and timing.
   Do not impose a start/stop/change format that alters the source wording.
   Explain jargon separately without changing the copied instruction.
9. Put return and urgent precautions under the neutral heading "When to call or come back," copied verbatim.
   Its content must be the clinician's words only: no added symptom, threshold, time frame, condition, or explanation.
   Never add a destination such as "go to the ER," "urgent care," "call 911," or "call the office" unless the clinician stated it.
   This restriction also applies to headings, labels, and lead-ins; do not introduce urgency or emergency labels.
   If the clinician named a destination, copy it exactly as written.
   If precautions are absent or withheld, omit this field and flag the gap in Part B and "Missing / to confirm."
10. Build Part B by checking each documented symptom and patient concern against the plan.
    Check allergies against planned medications, dose and unit inconsistencies, conflicting instructions, and conflicting results.
    Check for missing allergy information and other missing inputs that limit review.
    Check follow-up timing, location, and arrangements for documented tests or referrals; flag details needed to act that are absent.
    Do not assume an undocumented test or referral is required.
11. Phrase every Part B flag as a question to the clinician, quoting the source text that prompted it.
    For omissions, identify the relevant section and what it does not specify.
    Never turn a flag into patient advice.
    If no flags are identified, write "No flags identified; this does not establish clinical safety."
12. Build "Missing / to confirm" with one item per missing, unclear, conflicting, or withheld detail.
    Keep this list clinician-only; ensure each item has a corresponding Part B question.
    If there are no identified gaps, write "None identified."
13. Audit Part A line by line against the note.
    Remove unsupported medications, doses, targets, diagnoses, prognoses, warnings, and other clinical advice.
    Recheck each measurement against the inventory, character for character for values and units, and verify the count.
    Compare medication changes and precautions verbatim against the source.
    Check all Part A text, headings, labels, and lead-ins for added destinations, conditions, or urgency; remove any additions.
    Do not present the draft as approved or signed.

## Output format

```markdown
DRAFT — for clinician review before sharing with the patient.

## Part A — Your visit summary
Reason for your visit: <supported plain-language summary>
Your measurements and test results: <every recorded value and unit exactly; terms explained>
Findings: <documented findings; terms explained>
Medicines: <verbatim, unambiguous medication changes>
Next steps: <documented follow-up; exact timing>
When to call or come back: <the clinician's precaution words only, verbatim>

## Part B — Clinician check (not for the patient)
- <Question to clinician, with source quote or identified omission>

## Missing / to confirm
- <Clinician-only gap, conflict, or withheld instruction>
```

Omit unsupported Part A fields rather than filling them with assumptions; never omit a recorded measurement.
Retain the banner and all three section headings; replace placeholders with actual content.
Part B and "Missing / to confirm" are for clinician review only, not for the patient.

## Hard limits

- Never add a new medication, dose, target, diagnosis, prognosis, or warning to patient text.
- Never drop, round, convert, or independently interpret a recorded vital sign, measurement, or lab value.
- Never add a destination or condition to precautions that the clinician did not state, including in headings or labels.
- Never repair a suspected clinical error, resolve a contradiction independently, or imply that the check establishes safety.
- Input must be de-identified unless the organization confirms this tool is covered by its agreements and approved for the information; do not repeat unnecessary identifiers.
- US: under HIPAA, a cloud/AI service that creates, receives or maintains ePHI for a covered entity is a business associate and needs a BAA.
- HHS — HIPAA guidance on cloud computing (business associate agreements for cloud/AI services handling ePHI) — https://www.hhs.gov/hipaa/for-professionals/special-topics/health-information-technology/cloud-computing (checked 2026-10-19)
- The licensed, responsible clinician must verify clinical accuracy, every figure, medication change, precaution, and follow-up instruction against the source record, and resolve flagged concerns and gaps before sharing.
- The clinician signs; the summary is not medical advice from the tool. Remove Part B and "Missing / to confirm" from the patient version and review it after edits.
- UK/AU practitioners must verify applicable professional, privacy, and documentation requirements with their responsible organization or licensing body; the US statement does not establish their rules.
- Before sending or signing, see references/checklist.md.

## Example

Input (fictional; "Sample" is an invented case label):

```text
Case: Sample. Visit for knee pain. Vitals: BP 128/84 mmHg, weight 82 kg.
Assessment: knee strain. Patient also reports poor sleep.
Medication changes: none.
Plan: Follow up in 2 weeks.
Precautions: Call if knee pain worsens.
```

Output (abbreviated; proceeding with missing information flagged):

```markdown
DRAFT — for clinician review before sharing with the patient.
## Part A — Your visit summary
Reason for your visit: Knee pain.
Your measurements and test results: blood pressure (BP) 128/84 mmHg (millimeters of mercury, a pressure unit); weight 82 kg (kilograms).
Findings: Knee strain (an injury to a muscle or tendon around the knee).
Medicines: Medication changes: none.
Next steps: Follow up in 2 weeks.
When to call or come back: Call if knee pain worsens.
## Part B — Clinician check (not for the patient)
- Was "poor sleep" assessed, and does it need a plan?
- Where should follow-up occur? "Follow up in 2 weeks" gives no location.
- Can you confirm allergies and reactions? The note contains no allergy information.
## Missing / to confirm
- Plan for reported poor sleep; follow-up location.
- Allergy information.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Turn this visit note into the patient's after-visit summary.
[De-identified, fictional] 58-year-old, follow-up for type 2 diabetes and hypertension.
S: Feels well. Occasional tingling in both feet at night for 2 months. Ran out of lisinopril 1 week ago.
O: BP 152/94, HR 78, weight 94 kg (96 kg in June). A1c 8.1% (7.6% in June).
A/P: T2DM above goal. Increase metformin from 500 mg twice daily to 1000 mg twice daily with meals. Restart lisinopril 10 mg once daily. BP recheck at nurse visit in 2 weeks. A1c in 3 months. Call if dizziness or lightheadedness.
````

## Output (verbatim stdout, session metadata stripped)

DRAFT — for clinician review before sharing with the patient.

## Part A — Your visit summary

Reason for your visit: Follow-up visit for type 2 diabetes and high blood pressure (hypertension).

Your measurements and test results:
Blood pressure (BP): 152/94
Heart rate (HR): 78
Weight: 94 kg (kilograms). Your weight in June was 96 kg.
A1c (a blood test that measures your average blood sugar over time): 8.1%. Your A1c in June was 7.6%.

Findings: Type 2 diabetes (T2DM) — above goal.

Medicines:
Metformin (a medicine that helps control blood sugar): increase from 500 mg twice daily to 1000 mg twice daily with meals.
Lisinopril (a medicine that helps control blood pressure): restart 10 mg once daily.

Next steps:
Blood pressure recheck at a nurse visit in 2 weeks.
A1c in 3 months.

When to call or come back: Call if dizziness or lightheadedness.

## Part B — Clinician check (not for the patient)

- The note states "Occasional tingling in both feet at night for 2 months" — is this being addressed in the plan? No evaluation or follow-up for this symptom is documented.
- "BP 152/94" has no unit recorded — please confirm mmHg.
- "HR 78" has no unit recorded — please confirm bpm.
- The note states "Ran out of lisinopril 1 week ago" — should adherence or refill planning be addressed to prevent a recurrence before the next visit?
- A1c in 3 months is documented, but no location/method (lab draw, office, etc.) is specified — can you confirm where/how this will happen?
- The note contains no allergy information — can you confirm allergies and reactions?

## Missing / to confirm

- Unit for BP value (152/94).
- Unit for HR value (78).
- Plan/evaluation, if any, for reported bilateral foot tingling.
- Plan for preventing future lisinopril lapses (adherence/refill process).
- Location/method for the 3-month A1c.
- Allergy information.

