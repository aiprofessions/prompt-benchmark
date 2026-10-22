# Transcript — hc-en-soap-note-01 — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:08:37+00:00
- duration_s: 15.5
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c5d314dbf109d419f9ad162e2514af98c75fa3c24572c2cab3a18908bca2c0ca

## Query (verbatim, from query file)

```text
Draft a SOAP note from the de-identified primary-care transcript below.
Rules:
- Use only information stated in the transcript. Do not add exam findings, history or diagnoses that were not said.
- Record vitals and medication instructions exactly as stated.
- Put allergies where the clinician will see them first.
- End with "Missing / to confirm" listing anything a complete note would need that the transcript does not contain.
- Mark the note as a draft requiring clinician review and signature.
Transcript:
[De-identified, fictional] Adult patient, 34.
Patient: Sore throat for 3 days, hurts to swallow, fever last night. No cough. Kid at home had strep last week.
Clinician: Any allergies? Patient: Penicillin — I got a rash as a kid.
Nurse vitals: Temp 38.4 °C, HR 96, BP 122/78, SpO2 99% on room air.
Clinician exam (spoken): Tonsils swollen with white exudate. No rash.
Clinician: Let's do a rapid strep test now. If positive, we'll pick an antibiotic that isn't penicillin-based. Meanwhile ibuprofen 400 mg every 6 hours as needed with food. Come back or call if you can't swallow liquids or have trouble breathing.
```

## Output (verbatim stdout, session metadata stripped)

DRAFT — REQUIRES CLINICIAN REVIEW AND SIGNATURE. Not valid until reviewed and signed.

ALLERGIES: PENICILLIN — rash in childhood (patient-reported).

Patient: Adult, 34. (De-identified, fictional.)

SUBJECTIVE
  Chief complaint: Sore throat x 3 days.
  Reports pain on swallowing. Fever last night. Denies cough.
  Exposure: child at home had strep last week.

OBJECTIVE
  Vitals (nurse): Temp 38.4 °C, HR 96, BP 122/78, SpO2 99% on room air.
  Exam (clinician, as spoken): Tonsils swollen with white exudate. No rash.
  Rapid strep test: ordered, to be done now. Result not in transcript.

ASSESSMENT
  Sore throat with fever, tonsillar exudate, and household strep exposure. Clinician proceeding with rapid strep testing. No diagnosis was stated in the transcript.

PLAN
  1. Rapid strep test now.
  2. If positive: clinician to select an antibiotic that is not penicillin-based (specific agent not stated).
  3. Ibuprofen 400 mg every 6 hours as needed, with food.
  4. Return or call if unable to swallow liquids or if trouble breathing.

Missing / to confirm
  - Rapid strep result; any plan if negative (e.g. throat culture).
  - Specific antibiotic, dose, and duration if test is positive.
  - Duration/stop instructions for ibuprofen; contraindications check (renal, GI, pregnancy).
  - Past medical history, current medications, other allergies.
  - Social history (smoking etc.); pregnancy status if applicable.
  - Exam elements not mentioned: cervical lymph nodes, respiratory exam, ear exam, hydration status, respiratory rate.
  - Fever details: measured temperature at home, use of antipyretics before visit.
  - Other symptoms not addressed: headache, abdominal pain, rash history beyond "no rash" today.
  - Follow-up timing beyond the return precautions.
  - Patient identifiers, date/time of visit, clinician name and signature.

