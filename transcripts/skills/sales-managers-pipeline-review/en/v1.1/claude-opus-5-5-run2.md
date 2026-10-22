# Transcript — skill sales-managers-pipeline-review [en] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:34:38+00:00
- duration_s: 88.7
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c2395a433e484238f422ae288c2fa5dc3f9272124b7d2466afa17b37376583d4
- skill_sha256: 1465ce74591fa0a36ee3c3ed983ce401dbd34fd0b49a8c44e37c7eb16abc43d7

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Use when a sales manager pastes quarter dates, today's date, remaining quota, and deals to get a weighted forecast, quota gap, risk flags, coaching questions, and data gaps."
---

# Weekly Pipeline Review

## What it does

Prepares a weekly sales 1:1 or forecast review from a pasted deal list in a single reply. It calculates a weighted forecast for deals closing within the quarter and shows the gap to remaining quota. It identifies risks with their triggering rules, provides one coaching question per flagged deal, and lists missing information, labeled assumptions, and open questions. Forecast numbers are management estimates, not financial reporting.

## Inputs it expects

- Quarter end and quarter start, or the calendar or fiscal quarter convention.
- Today's date. Use the supplied date rather than substituting the system date.
- Remaining quota and currency, and whether signed or closed-won deals are already netted out of it.
- One row per deal: de-identified ID, amount, currency, stage, stated probability (%), close date, last activity date, next step, and relevant notes.
- Deal status: signed, closed-won, closed-lost, or open and unsigned.
- Team-defined stage versus close-date mismatch criteria, such as a minimum lead time for each stage.
- Only necessary CRM data. Use deal IDs and contact roles, not contact names, email addresses, or phone numbers.
- If something is missing, proceed with an allowed, clearly labeled assumption or [NOT PROVIDED], and list it with a question under Data gaps. Never guess deal facts.

## Procedure

1. Single-pass rule: always produce the complete output in the first reply.
   - Include all five sections, the full deal table, available arithmetic, the forecast total or its unavailable status, and the gap or its unavailable status.
   - Never stop to ask clarifying questions, promise a later draft, or withhold a section while waiting for answers.
   - Use only the review assumptions allowed below, each labeled "Assumption:"; otherwise write [NOT PROVIDED] and explain the affected calculation.
   - Never invent amounts, probabilities, close dates, contacts, activity, or next steps.
   - Put coaching questions in their required section and collect them again, with all clarification questions, under Data gaps. Do not require answers before delivering.
2. Minimize personal data before analysis. Omit unnecessary identifiers and use supplied de-identified deal IDs or neutral row labels.
3. Preserve supplied figures, stages, probabilities, dates, and relevant note wording without silently correcting them; remove unnecessary personal details.
   - Flag ambiguous dates, conflicting records, duplicate IDs, invalid amounts, future last-activity dates, and probabilities outside 0%–100%.
   - Do not double-count unresolved duplicates; list them as excluded pending resolution.
   - Do not convert currencies. Compute separate currency subtotals and a gap only against quota in the same currency.
   - Apply an explicitly stated review-wide currency to its deals. Otherwise leave unknown currencies unresolved; do not assume that "$" means USD.
4. Establish the quarter's inclusive start and end dates.
   - Use explicit dates or a supplied fiscal convention. If only a standard calendar-quarter end is supplied, label the inferred start "Assumption: calendar quarter."
   - Do not treat a nonstandard end date as a calendar-quarter end. If boundaries cannot be established, show them as unresolved and do not determine forecast eligibility.
   - If no quarter information is supplied but today is known, label "Assumption: calendar quarter containing today's date" and show its boundaries.
   - If today is missing, use an available system date only with "Assumption: today = <date used>"; otherwise mark it [NOT PROVIDED] and leave date-dependent checks unassessed.
5. Set the deal population against remaining quota.
   - Exclude explicit closed-lost deals with that reason.
   - Exclude signed or closed-won deals already reflected in remaining quota.
   - If their treatment is unstated, label "Assumption: remaining quota already nets out signed/closed-won deals" and exclude them.
   - If status is unstated, label "Assumption: <IDs> open and unsigned." This is a review assumption, not a CRM fact.
6. Classify every supplied deal and state the reason for each exclusion.
   - Include only deals whose close dates fall within the inclusive quarter boundaries, with a valid amount, stated probability, and known currency.
   - Exclude out-of-quarter deals, naming the close date and relevant boundary.
   - Keep deals with missing, invalid, or conflicting calculation inputs in the table, exclude them from calculable totals, and list the issue under Data gaps.
   - An overdue unsigned deal remains included if its close date is inside the quarter; do not move its date.
7. For each included deal, show amount × (stated probability ÷ 100) = weighted value.
   - Sum the values by currency and show the addition. Do not derive probabilities from stage names or treat missing probabilities as zero.
   - If unresolved deal inputs prevent a complete total, label it "partial — excludes <IDs>."
   - If no deal can be evaluated, report "Forecast unavailable" rather than a complete zero forecast.
   - Show zero when all deals are assessable and none qualifies; if only unresolved deals could contribute, show "Calculable subtotal: 0; forecast unavailable."
8. Show remaining quota − weighted forecast = gap for each matching currency.
   - Label any assumption or partial basis. A negative gap is coverage above remaining quota, not assured attainment.
   - If quota or forecast is unavailable, show the formula with [NOT PROVIDED] or [UNAVAILABLE] in place of the missing operand; do not invent a numeric gap.
   - If other-currency deals exist, identify the gap as quota-currency-only, not consolidated coverage.
9. Screen every supplied deal against these rules; report risks for active deals, including those excluded from the forecast.
   - R1 Past close date: close date < today and not signed. Label assumption-based status flags "R1 (on assumption)."
   - R2 Stale activity: today − last activity date >21 calendar days. Show the day count; exactly 21 days does not trigger it.
   - R3 No recorded next step: neither the next-step field nor notes contain a specific next action. Describe it as absent from the supplied record, not proof that no action exists.
   - R4 Champion/sponsor left: notes explicitly state the champion or sponsor departed. Quote the de-identified wording; a role change alone prompts a Data gaps question, not a departure flag.
   - R5 Stage versus close-date mismatch: apply only supplied criteria. Show the criterion, relevant stage or probability, and date calculation.
   - If criteria are absent, write "R5 not assessed: criteria [NOT PROVIDED]" and list the question under Data gaps.
   - Name checks that cannot be completed because dates, status, or notes are missing or invalid. Do not infer departure or inactivity from missing records.
   - Mark closed-lost or completed deals' active-deal checks as not applicable.
10. Write exactly one specific, open-ended coaching question per flagged deal.
    - Tie it to supplied facts; when several rules trigger, address the main issue.
    - Do not invent a contact, commitment, probability, or next step.
11. Under Data gaps, list every missing, invalid, ambiguous, or conflicting input and every assumption, naming the affected deal or review input and calculation or check.
    - Collect all clarification questions and repeat the coaching questions here without adding a second coaching question for any deal.
12. Produce the five output sections below in order; mark genuinely empty sections "None," not unassessed checks.
    - Label the output a management estimate, not financial reporting.
    - If AI-generated voice follow-up is proposed, include the US limitation and exact citation from Hard limits in Forecast summary; do not initiate calls.

## Output format

```markdown
DRAFT — management estimate for review, not financial reporting.
## Forecast summary
- Quarter: [start–end or unresolved] | Today: [date or [NOT PROVIDED]] | Currency: [currency]
- Assumptions: [each "Assumption: …" used, or "None"]
- Remaining quota: [amount or [NOT PROVIDED]]
- Weighted forecast [complete / partial / unavailable]: [addition = total, or reason]
- Gap: [quota] − [forecast] = [gap, or unavailable] ([basis/assumption label])
- Included: [count] | Excluded: [count, including unresolved deals]
## Deal table
| Deal ID | Status | Amount / currency | Stage / stated % | Close date | Eligibility / reason | Weighted arithmetic | Last activity | Recorded next step |
|---|---|---|---|---|---|---|---|---|
[One row per supplied deal; [NOT PROVIDED] for missing fields.]
## Risk flags
- [Deal ID] — [R# or R# (on assumption)] — [rule and triggering facts/calculation]
- [Unassessed checks and reasons, or "None"]
## Coaching questions
- [Flagged deal ID]: [exactly one specific question]
## Data gaps
- [Deal ID or review input] — [missing/conflicting item or assumption] — [affected calculation/check]
Open questions for the manager, including coaching questions:
1. [question]
```

## Hard limits

- Never stop to ask questions before drafting; deliver every section, available calculations, and explicit reasons for unavailable results.
- Never invent deal facts, probabilities, contacts, activity, next steps, or risk thresholds, or present assumptions as supplied facts.
- Never include an out-of-quarter deal or present a partial total as a complete forecast.
- Forecast numbers are management estimates, not financial reporting; do not present them as booked revenue or accounting figures.
- The responsible sales manager must verify assumptions, quarter boundaries, CRM accuracy, deal scope, remaining-quota treatment, currencies, arithmetic, risk criteria, and unresolved questions before using or sharing the review.
- CRM data is personal data of contacts: paste only what is necessary, de-identify contacts, and use only organization-approved tools for that data. Do not repeat unnecessary personal details.
- US: if follow-up uses AI-generated voice calls, the FCC's 2024 Declaratory Ruling (FCC-24-17) confirms the TCPA applies. The responsible professional, with counsel or compliance as appropriate, must verify applicable requirements and calling practices before any such calls.
- FCC Declaratory Ruling FCC-24-17 — the TCPA applies to AI-generated voices in calls — https://docs.fcc.gov/public/attachments/FCC-24-17A1.pdf (February 2024; checked 2026-10-19)
- For UK/AU use, do not claim local calling or privacy rules. The responsible professional must verify applicable local requirements with qualified counsel or compliance.
- Before sharing or acting on the review, see references/checklist.md.

## Example

Input (fictional; all amounts USD):
```text
Quarter ends 2026-12-31; today 2026-10-19; remaining quota $200,000; all deals open and unsigned.
Team mismatch rule: Discovery with 0–14 calendar days until close.
Example A: $100,000; Proposal 50%; close 2026-11-30; activity 2026-10-14; next: pricing call 2026-10-22; notes: no sponsor change.
Sample B: $80,000; Negotiation 75%; close 2026-10-10; activity 2026-09-20; next: missing; notes: champion left.
Sample C: $60,000; Discovery 25%; close 2027-01-15; activity 2026-10-16; next: demo; notes: no sponsor change.
```

Abbreviated output:
```markdown
## Forecast summary
DRAFT — management estimate, not financial reporting. Assumption: calendar quarter 2026-10-01–2026-12-31. Forecast: $50,000 + $60,000 = $110,000; gap: $200,000 − $110,000 = $90,000.
## Deal table
| Deal | Eligibility / reason | Weighted arithmetic |
|---|---|---|
| Example A | Included | $100,000 × (50 ÷ 100) = $50,000 |
| Sample B | Included despite overdue close | $80,000 × (75 ÷ 100) = $60,000 |
| Sample C | Excluded: 2027-01-15 > quarter end 2026-12-31 | Not included |
## Risk flags
Sample B — R1: 2026-10-10 < today, unsigned; R2: 29 days >21; R3: no recorded next step; R4: "champion left." R5: no flags; Sample C closes in 88 days, outside 0–14.
## Coaching questions
Sample B: What evidence supports keeping this deal in the quarter after the champion's departure?
## Data gaps
Quarter start assumed, affecting eligibility; Sample B next step [NOT PROVIDED], triggering R3.
Questions: Is the assumed quarter correct? What next step is recorded for Sample B? Coaching question repeated: What evidence supports keeping this deal in the quarter after the champion's departure?
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

DRAFT: Management estimate for review, not financial reporting. You must verify the assumptions, quarter boundaries, CRM accuracy, currency, arithmetic, and open questions before you use or share this review.

FORECAST SUMMARY

  Quarter: 2027-01-01 to 2027-03-31 | Today: 2027-01-18 (as supplied) | Currency: "$" as supplied (USD not assumed)

  Assumptions:
    Assumption: calendar quarter. Only the end date was supplied, so the start is inferred as 2027-01-01.
    Assumption: Orion Example, Bluefin Sample, Delta Example and Elm Sample are open and unsigned. Cedar Test Co is stated as not signed.
    No signed or closed-won deals were listed, so the quota-netting assumption does not apply.

  Remaining quota: $400,000

  Weighted forecast: UNAVAILABLE. Calculable subtotal is $0.
    Close dates for deals 1 to 4 have no year ("Mar 15", "Feb 28", "Jan 10", "Mar 30"). I can't confirm their quarter eligibility without guessing.
    Elm Sample is the only deal with a full date (2027-04-20), and it falls outside the quarter.

  Conditional, not the forecast: if you confirm all year-less close dates are 2027:
    $140,000 + $36,000 + $45,000 + $26,000 = $247,000

  Gap: $400,000 − [UNAVAILABLE] = unavailable.
    Conditional (2027 close dates): $400,000 − $247,000 = $153,000.

  Included: 0 confirmed (4 pending close-date year) | Excluded: 1 (Elm, out of quarter)

DEAL TABLE

  1) Orion Example
     Status: open/unsigned (assumption)
     Amount: $200,000 | Stage: Negotiation, 70%
     Close: "Mar 15" (no year)
     Eligibility: pending year confirmation. In quarter if 2027.
     Arithmetic: $200,000 × (70 ÷ 100) = $140,000 (conditional)
     Last activity: "Jan 15" (no year) | Next step: [NOT PROVIDED]
     Note: "our only contact is the CFO"

  2) Bluefin Sample
     Status: open/unsigned (assumption)
     Amount: $90,000 | Stage: Proposal, 40%
     Close: "Feb 28" (no year)
     Eligibility: pending year confirmation. In quarter if 2027.
     Arithmetic: $90,000 × (40 ÷ 100) = $36,000 (conditional)
     Last activity: "Dec 10" (no year) | Next step: [NOT PROVIDED]

  3) Cedar Test Co
     Status: open, not signed (supplied)
     Amount: $50,000 | Stage: Commit, 90%
     Close: "Jan 10" (no year)
     Eligibility: pending year confirmation. In quarter if 2027. It stays included even though overdue, and the date is not moved.
     Arithmetic: $50,000 × (90 ÷ 100) = $45,000 (conditional)
     Last activity: "Jan 9" (no year) | Next step: [NOT PROVIDED]
     Note: "legal review pending, not signed"

  4) Delta Example
     Status: open/unsigned (assumption)
     Amount: $130,000 | Stage: Discovery, 20%
     Close: "Mar 30" (no year)
     Eligibility: pending year confirmation. In quarter if 2027.
     Arithmetic: $130,000 × (20 ÷ 100) = $26,000 (conditional)
     Last activity: "Jan 16" (no year) | Next step: [NOT PROVIDED]

  5) Elm Sample
     Status: open/unsigned (assumption)
     Amount: $75,000 | Stage: Proposal, 40%
     Close: 2027-04-20
     Eligibility: EXCLUDED. 2027-04-20 is after the quarter end of 2027-03-31.
     Arithmetic: not included
     Last activity: "Jan 17" (no year) | Next step: [NOT PROVIDED]

RISK FLAGS

  Cedar Test Co
    R1 (pending year): close "Jan 10" is before today (2027-01-18) if the year is 2027, and the deal is stated as not signed.
    R3: no specific next action recorded. "Legal review pending" describes a status, not a dated action.

  Bluefin Sample
    R2: reading "Dec 10" as 2026-12-10 gives 2027-01-18 − 2026-12-10 = 39 days, which is over 21. Any earlier year makes it staler.
    R3 (on assumption): no next step or notes supplied.

  Orion Example
    R3 (on assumption): no next step supplied. The note ("our only contact is the CFO") contains no action.

  Delta Example
    R3 (on assumption): no next step or notes supplied.

  Elm Sample
    R3 (on assumption): no next step or notes supplied. The deal is out of quarter but still active.

  R3 reflects what is absent from the supplied record, not proof that no action exists.

  Not assessed or incomplete:
    R5 not assessed: stage versus close-date criteria [NOT PROVIDED].
    R4: no departure is stated in any supplied note. Bluefin, Delta and Elm had no notes, so R4 was checked only against what was given.
    R1 for deals 1, 2 and 4: not triggered if their close dates are in 2027.
    R2 for deals 1, 3, 4 and 5: 3, 9, 2 and 1 days respectively if their activity dates are in 2027, so not triggered. These counts need year confirmation.

COACHING QUESTIONS

  Orion Example: With the CFO as your only contact, what is the next scheduled step that gets this Negotiation deal to signature by Mar 15?
  Bluefin Sample: What has the customer done since the Dec 10 activity that still supports a Feb 28 close?
  Cedar Test Co: Now that the Jan 10 close has passed, what date has the customer committed to for completing legal review and signing?
  Delta Example: What concrete next step moves Delta beyond Discovery, and when is it scheduled?
  Elm Sample: What next action is scheduled on Elm, and what is driving the Apr 20 close date?

DATA GAPS

  Quarter start: not supplied. Assumption: calendar quarter (2027-01-01). Affects eligibility for all deals.
  Close-date year for Orion, Bluefin, Cedar and Delta: missing. Affects eligibility, the forecast total, the gap, and R1.
  Last-activity year for all deals: missing. Bluefin is read as 2026-12-10 for the R2 day count. Affects R2.
  Currency: "$" is not identified (USD, CAD, AUD, etc.). Figures are used as written with no conversion, and the comparison to quota assumes they share one currency. Affects all totals and the gap.
  Status for Orion, Bluefin, Delta and Elm: unstated. Assumption: open and unsigned. Affects R1 and population.
  Quota netting: unstated whether any already-signed deals are reflected in the $400,000. Affects the gap.
  Next-step field: not provided for any deal. Affects R3.
  Notes: none for Bluefin, Delta or Elm. Affects R3 and R4.
  Stage versus close-date criteria: not provided. Affects R5. For example, Delta is at Discovery 20% with a Mar 30 close and cannot be evaluated.
  Orion contact coverage: the CFO is the only recorded contact. No departure is stated. Context only, not an R4 flag.

  Open questions for you:
    1. Are all year-less close dates (Mar 15, Feb 28, Jan 10, Mar 30) in 2027?
    2. Are the last-activity dates Jan 2027 and Dec 10, 2026?
    3. Is the quarter Jan 1 to Mar 31, 2027?
    4. Which currency is "$", and is it the same for quota and every deal?
    5. Are Orion, Bluefin, Delta and Elm all open and unsigned?
    6. Does the $400,000 already net out any signed or closed-won deals this quarter?
    7. What next step is recorded in the CRM for each deal?
    8. What stage versus close-date rules should R5 use?
    9. Orion: With the CFO as your only contact, what is the next scheduled step that gets this Negotiation deal to signature by Mar 15?
    10. Bluefin: What has the customer done since the Dec 10 activity that still supports a Feb 28 close?
    11. Cedar: Now that the Jan 10 close has passed, what date has the customer committed to for completing legal review and signing?
    12. Delta: What concrete next step moves Delta beyond Discovery, and when is it scheduled?
    13. Elm: What next action is scheduled on Elm, and what is driving the Apr 20 close date?

