# Transcript — skill sales-managers-pipeline-review [en] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:10:43+00:00
- duration_s: 40.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c2395a433e484238f422ae288c2fa5dc3f9272124b7d2466afa17b37376583d4
- skill_sha256: 4a6b2f2bc158740a377dcf2b462eaa55ad32e955efd247262dfb2c26181e8905

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Use when a sales manager pastes quarter dates, today's date, remaining quota, and deals to get a weighted forecast, quota gap, risk flags, coaching questions, and data gaps."
---

# Weekly Pipeline Review

## What it does

Prepares a weekly sales 1:1 or forecast review from a pasted deal list. It calculates a weighted forecast for deals closing within a confirmed quarter and shows the gap to remaining quota. It identifies risks with their triggering rules, asks one coaching question per flagged deal, and lists missing information. Forecast numbers are management estimates, not financial reporting.

## Inputs it expects

- Quarter end and quarter start, or an explicit statement of the calendar or fiscal quarter convention.
- Today's date; use the supplied date rather than substituting the system date.
- Remaining quota and currency; confirm how signed or closed-won deals have already affected it.
- One row per deal: de-identified ID, amount, currency, stage, stated probability (%), close date, last activity date, next step, and relevant notes.
- Deal status, including whether signed, closed-won, closed-lost, or open and unsigned.
- Team-defined stage versus close-date mismatch criteria, such as a stated minimum lead time for each stage.
- Paste only necessary CRM data, using deal IDs and contact roles rather than contact names, email addresses, or phone numbers.
- Ask once in a consolidated request for missing inputs or clarification. If unavailable, proceed only with supported calculations and list every unresolved item under Data gaps; never guess.

## Procedure

1. Minimize personal data before analysis. Omit unnecessary identifiers from the response and use supplied deal IDs or neutral row labels.
2. Preserve supplied figures, stages, probabilities, dates, and notes without silently correcting them.
   - Flag ambiguous dates, conflicting records, duplicate IDs, invalid amounts, and probabilities outside 0%–100%.
   - Do not convert currencies or combine different currencies into one total. Request a common-currency input if needed.
3. Establish the quarter's inclusive start and end dates from explicit inputs or the user's confirmed quarter convention.
   - Never infer that the quarter is a calendar quarter from its end date alone.
   - If either boundary is unresolved, withhold the quarter forecast and gap; mark date eligibility unverified.
4. Confirm the deal population against remaining quota.
   - Exclude explicit closed-lost deals with that reason.
   - Exclude signed or closed-won deals already reflected in remaining quota to avoid double-counting.
   - If their treatment is unclear, withhold those contributions and list the unresolved treatment; do not assume quota already nets them out.
5. Classify every supplied deal and state the reason for each exclusion or withheld contribution.
   - Include only deals whose close dates are on or after quarter start and on or before quarter end, with valid amounts and stated probabilities.
   - Exclude out-of-quarter deals, naming the close date and relevant boundary.
   - Withhold contributions with missing or invalid calculation fields, ambiguous dates, or unresolved scope.
   - An overdue unsigned deal can remain included if its close date is inside the quarter; do not move its date.
6. For each included deal, show amount × (stated probability ÷ 100) = weighted value.
   - Sum the values and show the addition, including a zero total if all deals are definitively excluded.
   - Do not treat a missing probability as zero or derive it from a stage name.
   - If unresolved deals could affect the total, label the result a partial subtotal, not a complete forecast.
7. Show remaining quota − weighted forecast = gap, using matching currencies.
   - Label a negative gap as coverage above remaining quota, not assured attainment.
   - Withhold the gap if quota, quarter boundaries, or a complete comparable forecast are unavailable.
8. Screen every supplied deal for these rules; report relevant risks for active deals, including those excluded from the forecast.
   - R1 Past close date: close date < today and explicitly unsigned. If signing status is unknown, record a possible R1 requiring confirmation, not a confirmed unsigned deal.
   - R2 Stale activity: today − last activity date >21 calendar days. Show the day count; exactly 21 days does not trigger it.
   - R3 No recorded next step: neither the next-step field nor notes contains a specific next action. Flag the absence in the supplied record, not an assertion that no action exists.
   - R4 Champion/sponsor left: notes explicitly state that the champion or sponsor departed. Quote the relevant de-identified wording; a role change alone requires clarification.
   - R5 Stage versus close-date mismatch: apply only user-supplied criteria. State the criterion, the stage or probability, and the date calculation that triggered it.
   - If R5 criteria are absent, list “Stage versus close-date mismatch not assessed: criteria missing” under Data gaps.
   - For missing or conflicting dates, status, or notes, state which risk check cannot be completed. Do not infer a departure or absence of activity.
   - Mark explicitly closed-lost or completed deals' active-deal risk checks as not applicable.
9. Write exactly one specific, open-ended coaching question per deal with a confirmed or possible flag.
   - Tie it to supplied facts and prioritize the main issue when multiple rules trigger.
   - Ask for clarification or the manager's judgment; do not invent a contact, commitment, probability, or next step.
10. List all missing, invalid, ambiguous, or conflicting inputs under Data gaps, naming the affected deal or review input and the calculation or check affected.
11. Produce the five output sections below in order, including empty sections marked “None.”
   - Label the result as a management estimate, not financial reporting.
   - If AI-generated voice follow-up is proposed, include the US limitation and exact citation from Hard limits in Forecast summary; do not initiate calls.

## Output format

```markdown
## Forecast summary
- Quarter: [start–end] | Today: [date] | Currency: [currency]
- Remaining quota: [amount or unavailable]
- Weighted forecast [or partial subtotal]: [addition] = [total or unavailable]
- Gap: [quota] − [complete forecast] = [gap, or withheld with reason]
- Included: [count] | Excluded: [count] | Withheld: [count]
- Management estimate, not financial reporting.
## Deal table
| Deal ID | Status | Amount | Stage / stated % | Close date | Eligibility / reason | Weighted arithmetic | Last activity | Recorded next step |
|---|---|---|---|---|---|---|---|---|
[One row per supplied deal; identify every exclusion and withheld contribution.]
## Risk flags
- [Deal ID] — [confirmed or possible R#] — [rule and triggering facts/calculation]
## Coaching questions
- [Flagged deal ID]: [exactly one specific question]
## Data gaps
- [Deal ID or review input] — [missing/conflicting item] — [affected calculation/check and confirmation needed]
```

## Hard limits

- Never invent deal facts, probabilities, contacts, activity, next steps, quarter conventions, or risk thresholds.
- Never include an out-of-quarter deal or present an incomplete subtotal as a complete forecast.
- Forecast numbers are management estimates, not financial reporting; do not present them as booked revenue or accounting figures.
- The responsible sales manager must verify quarter boundaries, CRM accuracy, deal scope, remaining-quota treatment, arithmetic, risk criteria, and unresolved inputs before using or sharing the review.
- CRM data is personal data of contacts: paste only what is necessary, de-identify contacts, and use only organization-approved tools for that data. Do not repeat unnecessary personal details.
- US: if follow-up uses AI-generated voice calls, the FCC's 2024 Declaratory Ruling (FCC-24-17) confirms the TCPA applies. The responsible professional, with counsel or compliance as appropriate, must verify applicable requirements and calling practices before any such calls.
- FCC Declaratory Ruling FCC-24-17 — the TCPA applies to AI-generated voices in calls — https://docs.fcc.gov/public/attachments/FCC-24-17A1.pdf (February 2024; checked 2026-10-19)
- For UK/AU use, do not claim local calling or privacy rules. The responsible professional must verify applicable local requirements with qualified counsel or compliance.
- Before sharing or acting on the review, see references/checklist.md.

## Example

Input (fictional; all amounts USD):
```text
Quarter 2026-10-01–2026-12-31; today 2026-10-19; remaining quota $200,000; all listed deals open and unsigned.
Team mismatch rule: Discovery with 0–14 calendar days until close; no other stage/date criteria.
Example A: $100,000; Proposal 50%; close 2026-11-30; activity 2026-10-14; next: pricing call 2026-10-22.
Sample B: $80,000; Negotiation 75%; close 2026-10-10; activity 2026-09-20; next: missing; notes: champion left.
Muestra C: $60,000; Discovery 25%; close 2027-01-15; activity 2026-10-16; next: demo.
```

Abbreviated output:
```markdown
## Forecast summary
- Weighted forecast: $50,000 + $60,000 = $110,000; gap: $200,000 − $110,000 = $90,000.
- Management estimate, not financial reporting.
## Deal table
- Example A included: $100,000 × (50 ÷ 100) = $50,000; Sample B included: $80,000 × (75 ÷ 100) = $60,000.
- Muestra C excluded: 2027-01-15 is after quarter end 2026-12-31.
## Risk flags
- Sample B — confirmed R1: unsigned, 2026-10-10 < today; R2: 29 days >21; R3: no recorded next step; R4: “champion left.”
- R5: no trigger under supplied Discovery/0–14-day criterion; Muestra C closes in 88 days.
## Coaching questions
- Sample B: What evidence supports keeping this unsigned deal in the quarter after the champion's departure?
## Data gaps
- Sample B — next step missing; confirm the intended action for the review.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prep my weekly pipeline review.
Quarter ends Mar 31, 2027. Today: Jan 18, 2027. Remaining quota for the quarter: $400,000.
1) Orion Example — $200,000 — Negotiation (70%) — close Mar 15 — last activity Jan 15 — our only contact is the CFO.
2) Bluefin Sample — $90,000 — Proposal (40%) — close Feb 28 — last activity Dec 10.
3) Cedar Test Co — $50,000 — Commit (90%) — close Jan 10 — last activity Jan 9 — legal review pending, not signed.
4) Delta Example — $130,000 — Discovery (20%) — close Mar 30 — last activity Jan 16.
5) Elm Sample — $75,000 — Proposal (40%) — close Apr 20, 2027 — last activity Jan 17.
````

## Output (verbatim stdout, session metadata stripped)

FORECAST SUMMARY

  Quarter: start not provided – end 2027-03-31 | Today: 2027-01-18 | Currency: "$" (code not confirmed)
  Remaining quota: $400,000
  Weighted forecast: withheld. The quarter start date and convention were not provided, so date eligibility can't be confirmed for deals 1–4.
  Gap: withheld. There is no complete forecast to compare with the quota.
  Included: 0 | Excluded: 1 (Elm) | Withheld: 4 (Orion, Bluefin, Cedar, Delta)
  This is a management estimate, not financial reporting.

  The per-deal arithmetic is shown below. It is not totaled until the quarter start and the close-date years are confirmed.


DEAL TABLE

  Orion Example
    Status: open; signing status not stated
    Amount: $200,000
    Stage / %: Negotiation / 70%
    Close date: Mar 15 (year not stated)
    Eligibility: withheld (quarter start unknown; year missing)
    Arithmetic: $200,000 × (70 ÷ 100) = $140,000, pending eligibility
    Last activity: Jan 15
    Next step: none recorded

  Bluefin Sample
    Status: open; signing status not stated
    Amount: $90,000
    Stage / %: Proposal / 40%
    Close date: Feb 28 (year not stated)
    Eligibility: withheld (quarter start unknown; year missing)
    Arithmetic: $90,000 × (40 ÷ 100) = $36,000, pending eligibility
    Last activity: Dec 10 (year not stated)
    Next step: none recorded

  Cedar Test Co
    Status: open, explicitly "not signed"
    Amount: $50,000
    Stage / %: Commit / 90%
    Close date: Jan 10 (year not stated)
    Eligibility: withheld (quarter start unknown; Jan 10 could fall before a non-calendar start)
    Arithmetic: $50,000 × (90 ÷ 100) = $45,000, pending eligibility
    Last activity: Jan 9
    Next step: none recorded ("legal review pending" is a status, not an action)

  Delta Example
    Status: open; signing status not stated
    Amount: $130,000
    Stage / %: Discovery / 20%
    Close date: Mar 30 (year not stated)
    Eligibility: withheld (quarter start unknown; year missing)
    Arithmetic: $130,000 × (20 ÷ 100) = $26,000, pending eligibility
    Last activity: Jan 16
    Next step: none recorded

  Elm Sample
    Status: open; signing status not stated
    Amount: $75,000
    Stage / %: Proposal / 40%
    Close date: 2027-04-20
    Eligibility: EXCLUDED. The close date is after the quarter end of 2027-03-31.
    Arithmetic: n/a
    Last activity: Jan 17
    Next step: none recorded


RISK FLAGS

  Cedar Test Co
    Confirmed R1: explicitly not signed, and close Jan 10 is before today (Jan 18), 8 days overdue, assuming the year is 2027.
    R3: no specific next action recorded.

  Bluefin Sample
    Confirmed R2: last activity was 39 days ago (Dec 10, 2026 to Jan 18, 2027, assuming 2026), which exceeds 21 days.
    R3: no next step recorded.

  Orion Example
    R3: no next step recorded.
    Not flagged for R4: the notes say the CFO is the only contact, but nothing says a champion or sponsor left.

  Delta Example
    R3: no next step recorded.

  Elm Sample
    R3: no next step recorded. Elm is excluded from the forecast but still active.

  No deal triggers R2 except Bluefin. Day counts since last activity:
    Orion: 3 days
    Cedar: 9 days
    Delta: 2 days
    Elm: 1 day

  R5 (stage vs. close date) was not assessed because the criteria are missing. See Data gaps.


COACHING QUESTIONS

  Cedar Test Co: Legal review is pending and the Jan 10 close date has passed. What specifically has to happen in legal, and by when, for this to sign?

  Bluefin Sample: After 39 days with no recorded activity, what tells you this deal is still live for a Feb 28 close?

  Orion Example: With the CFO as the only recorded contact, what is the next agreed step that moves this $200,000 deal toward a Mar 15 close?

  Delta Example: What has to be confirmed in discovery, and by when, to support a Mar 30 close for this deal?

  Elm Sample: What is the agreed next action, and what is driving the Apr 20 close date rather than an earlier one?


DATA GAPS

  Quarter start date or convention (calendar or fiscal)
    Affects: all eligibility checks, the forecast total and the gap.

  Close-date years for Orion, Bluefin, Cedar and Delta, and the last-activity year for Bluefin
    Affects: eligibility, the R1 check for Cedar and the R2 day count for Bluefin.

  Signing status for Orion, Bluefin, Delta and Elm
    Affects: confirming the open-deal treatment, and whether any deal is already netted out of the $400,000 quota.

  Remaining-quota treatment
    Confirm that the $400,000 already excludes all signed or closed-won deals, to avoid double-counting.

  Currency
    Confirm that "$" means USD for every deal and for the quota.

  Next steps for all five deals
    None are recorded, so R3 is flagged for each. Please supply the intended next actions.

  R5 criteria
    Stage vs. close-date mismatch was not assessed because the criteria are missing. A minimum lead time per stage is needed. This matters especially for Delta, which is in Discovery with a Mar 30 close.


TO COMPLETE THE FORECAST, PLEASE SEND

  1. The quarter start date, or confirmation that it is the calendar quarter, 2027-01-01 to 2027-03-31.
  2. The close-date years for deals 1–4.
  3. The signing status of deals 1, 2, 4 and 5.
  4. Confirmation that the quota is net of signed deals.
  5. Confirmation that "$" is USD.
  6. Your stage/close-date mismatch rule.

Before using or sharing this review, verify the quarter boundaries, CRM data, quota treatment and arithmetic against references/checklist.md.

