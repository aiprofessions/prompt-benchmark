# Transcript — skill healthcare-visit-summary [en] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:13:14+00:00
- duration_s: 33.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e88c591c65d269456b408fbd7e79e5a4f556c220c58d8afcc0acc5c79f8bfdde
- skill_sha256: 58fcead670cf95d1fe6a325d236c8060ac31f1ed4b55f59d615909d58b16eb0b

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Use when a clinician pastes a visit note to draft a plain-language patient summary, a clinician-only red-flag check, and a missing-information list."
---

# Patient-Friendly Visit Summary + Red-Flag Check

## What it does

Drafts a patient-friendly after-visit summary from a clinician's or nurse's visit note.
Separately checks for unaddressed concerns, contradictions, and missing follow-up details.
The responsible clinician reviews, resolves questions, and signs before any patient-facing text is shared.

## Inputs it expects

- A de-identified visit note, unless the organization has confirmed that this tool is covered by its agreements and approved for this information.
- The reason for the visit, assessment, and plan as documented.
- Medication information, including changes, doses, units, frequency, and timing.
- Allergies and any documented reactions.
- Results discussed, with their recorded values and units.
- Follow-up instructions and return or urgent precautions.
- Optional: patient communication needs and practice jurisdiction.

If essential information is missing, ask once in one consolidated message.
If the user requests a draft without clarification, proceed using only supported content and list the gaps under "Missing / to confirm."
Do not infer missing facts or treat an absent allergy list as confirmation of no allergies.

## Procedure

1. Check privacy before drafting.
   If apparent identifiers are present and organizational approval has not been confirmed, stop and request a de-identified note or confirmation of approved use.
   Do not repeat identifiers in the request or draft; an explicitly fictional example label is not a real patient identifier.
2. Identify the reason for the visit, findings, plan, medications, allergies, concerns, follow-up, and precautions.
   Record missing or conflicting information; ask for clarification as described above.
3. Start every summary draft with "DRAFT — for clinician review before sharing with the patient."
   Use the four output sections below in their stated order.
4. Check source instructions for ambiguity or contradictions before putting them in Part A.
   Withhold disputed medication directions, unclear precautions, or other conflicting instructions pending confirmation.
   Quote the relevant source wording in Part B as a question and list the unresolved item under "Missing / to confirm."
   Do not choose between conflicting versions or silently repair a suspected error.
5. Write Part A at approximately a 6th–8th grade reading level.
   Use short sentences, common words, and "you" or "your"; explain each medical term or abbreviation on first use.
   Keep explanations general and nonnumeric, such as "A1c (a blood test that measures average blood sugar)."
   Do not add a diagnosis, prognosis, interpretation of a result, or clinical instruction through an explanation.
6. Copy every included number, dose, unit, frequency, duration, and follow-up date exactly from the note.
   Do not round, convert, calculate, normalize notation, or insert a missing unit.
   Do not introduce numbers through explanations; do not reproduce irrelevant figures solely because they appear in the note.
7. Copy each unambiguous medication change verbatim, including the drug, dose, units, frequency, and timing.
   Do not impose a start/stop/change format that alters the source wording.
   Explain jargon separately without changing the copied instruction.
8. Copy return and urgent precautions verbatim, without simplifying their wording or thresholds.
   Use the neutral label "Return and urgent precautions"; do not recast a routine call instruction as an emergency.
   If precautions are absent, do not invent them; flag their absence for clinician confirmation.
9. Build Part B by checking each documented symptom and patient concern against the plan.
   Also check allergies against planned medications, dose and unit inconsistencies, conflicting medication instructions, and conflicting results.
   Check whether documented follow-up specifies enough detail to act, including timing, destination, and arrangements for any ordered tests or referrals.
   Do not assume that an undocumented test or referral is required.
10. Phrase every Part B flag as a question to the clinician and quote the source text that prompted it.
    For omissions, identify the relevant section and what it does not specify.
    Never turn a flag into patient advice; if no flags are identified, state that this does not establish clinical safety.
11. Build "Missing / to confirm" with one item per missing, unclear, conflicting, or withheld detail.
    Keep this list clinician-only; if there are no identified gaps, write "None identified."
12. Audit Part A line by line against the note.
    Remove unsupported medications, doses, targets, diagnoses, prognoses, warnings, and other clinical advice.
    Verify exact figures, verbatim medication changes and precautions, plain term explanations, and separation of clinician-only content.
    Do not present the draft as approved or signed.

## Output format

```markdown
DRAFT — for clinician review before sharing with the patient.

## Part A — Your visit summary
Reason for your visit: <supported plain-language summary>
Findings: <documented findings; exact figures; explained terms>
Medicines: <verbatim, unambiguous medication changes>
Next steps: <documented follow-up; exact timing>
Return and urgent precautions: <verbatim clinician instructions>

## Part B — Clinician check (not for the patient)
- <Question to clinician, with source quote or identified omission>

## Missing / to confirm
- <Clinician-only gap, conflict, or withheld instruction>
```

Omit unsupported Part A fields rather than filling them with assumptions.
Retain all four output sections; replace placeholders with actual content.

## Hard limits

- Never add new medication, dose, target, diagnosis, prognosis, or warning to patient text.
- Never repair a suspected clinical error, resolve a contradiction independently, or imply that the check establishes safety.
- Input must be de-identified unless the organization confirms this tool is covered by its agreements and approved for the information; do not repeat unnecessary identifiers.
- US: under HIPAA, a cloud/AI service that creates, receives or maintains ePHI for a covered entity is a business associate and needs a BAA.
- HHS — HIPAA guidance on cloud computing (business associate agreements for cloud/AI services handling ePHI) — https://www.hhs.gov/hipaa/for-professionals/special-topics/health-information-technology/cloud-computing (checked 2026-10-19)
- The licensed, responsible clinician must verify clinical accuracy, every figure, medication change, precaution, and follow-up instruction against the source record, and resolve flagged concerns and gaps before sharing.
- The clinician signs; the summary is not medical advice from the tool. Remove Part B and "Missing / to confirm" from the patient version.
- UK/AU practitioners must verify local professional, privacy, and documentation requirements with their responsible organization or licensing body; do not treat the US statement as their rules.
- Before sending or signing, see references/checklist.md.

## Example

Input (fictional; "Sample" is an invented case label):

```text
Case: Sample. Visit for knee pain.
Assessment: knee strain. Patient also reports poor sleep.
Medication changes: none.
Plan: Follow up in 2 weeks.
Precautions: Call if knee pain worsens.
```

Output (abbreviated):

```markdown
DRAFT — for clinician review before sharing with the patient.
## Part A — Your visit summary
You came in for knee pain.
You have a knee strain (an injury to a muscle or tendon around the knee).
Next steps: Follow up in 2 weeks.
Return and urgent precautions: Call if knee pain worsens.
## Part B — Clinician check (not for the patient)
- Was "poor sleep" assessed, and does it need a plan?
- Where should follow-up occur? The plan says "Follow up in 2 weeks" but gives no location.
## Missing / to confirm
- Follow-up location.
- Plan for reported poor sleep.
- Allergy information not supplied.
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

Reason for your visit: You came in for a follow-up visit for your type 2 diabetes and high blood pressure (hypertension).

Findings: You said you feel well overall. You have had tingling in both feet at night for the past 2 months. Your blood pressure was 152/94. Your heart rate was 78. Your weight was 94 kg (it was 96 kg in June). Your A1c (a blood test that measures your average blood sugar) was 8.1%. In June, it was 7.6%.

Medicines: Increase metformin from 500 mg twice daily to 1000 mg twice daily with meals. Restart lisinopril 10 mg once daily.

Next steps: Blood pressure recheck at a nurse visit in 2 weeks. A1c in 3 months.

Return and urgent precautions: Call if dizziness or lightheadedness.

## Part B — Clinician check (not for the patient)

- The note says "Occasional tingling in both feet at night for 2 months," but the assessment/plan doesn't mention this symptom. Was it evaluated, and does it need a plan (e.g., diabetic neuropathy workup)?
- No allergy information is documented. Should allergies be confirmed before the metformin increase and lisinopril restart are communicated to the patient?
- "A1c in 3 months" doesn't specify where/how the test should be done (e.g., lab order now, at next visit). Is this detail available?
- Patient "Ran out of lisinopril 1 week ago" — is there any clinical concern about the 1-week gap (e.g., BP control, kidney function) that should be addressed in the plan or communicated to the patient?

This check does not establish clinical safety; it only flags items for your review.

## Missing / to confirm

- Allergy information not supplied.
- Plan for reported tingling in both feet (duration 2 months, nocturnal) is not documented.
- Location/arrangement for the 3-month A1c is not specified.
- Clinical significance (if any) of the 1-week lapse in lisinopril is not documented.

