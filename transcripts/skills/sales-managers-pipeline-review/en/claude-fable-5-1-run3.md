# Transcript — skill sales-managers-pipeline-review [en] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:40:37+00:00
- duration_s: 45.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c2395a433e484238f422ae288c2fa5dc3f9272124b7d2466afa17b37376583d4
- skill_sha256: 14fdac82ea61db5537f937b401f42057f6acdefeb64d3ff301c4eaaa166dc47e

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Use when a sales manager pastes quarter dates, today's date, remaining quota, and deals to receive forecast arithmetic, quota gap, risk flags, coaching questions, and data gaps."
---

# Weekly Pipeline Review

## What it does

Prepares a weekly sales 1:1 or forecast review from a pasted pipeline. Calculates a weighted forecast and remaining-quota gap, shows exclusions, and flags deal risks with their triggering rules. Provides one coaching question per flagged deal and identifies missing inputs. Forecast numbers are management estimates, not financial reporting.

## Inputs it expects

- Quarter end; quarter start or fiscal quarter convention if available.
- Today's date, remaining quota, and currency.
- Each deal's de-identified ID, amount, stage, stated probability (%), close date, last activity date, next step, and relevant notes.
- Distinct contacts identified by anonymous labels and roles, preserving the number of people without disclosing names.
- Explicit won, lost, signed, or closed status where applicable; otherwise treat the deal as open.
- Team-defined stage versus close-date mismatch criteria, such as minimum lead time by stage.
- Paste only necessary CRM data; omit contact names, email addresses, phone numbers, and unrelated personal information.
- If quota, currency, or usable quarter context is missing, ask once for the missing review inputs. Otherwise proceed using the defaults below and list missing deal fields; never guess them.
- If essential inputs remain missing after that request, provide the supported calculations and identify the missing operand rather than inventing a figure.

## Procedure

1. Minimize data before analysis.
   - Use de-identified deal IDs and distinct anonymous contact labels with roles.
   - Do not reproduce unnecessary personal data from the paste.
2. Preserve and validate the supplied records.
   - Copy amounts, probabilities, stages, and relevant facts faithfully; show normalized dates alongside any ambiguous original date.
   - Flag invalid amounts, probabilities outside 0%–100%, future activity dates, and conflicting records.
   - Count exact duplicate rows once and identify them. Exclude conflicting duplicate records pending clarification; retain their IDs and reasons.
   - Never infer probabilities from stage names or invent amounts, contacts, activity, or next steps.
3. Establish dates and list each assumption once below the forecast and gap.
   - Use supplied today; if absent, use the system date and state that assumption.
   - Use explicit quarter boundaries or the supplied fiscal convention.
   - If only quarter end is supplied, assume a three-calendar-month period ending on that date: start = end plus one day minus three calendar months. Flag this for verification.
   - If neither boundaries nor fiscal context is supplied, request it once rather than inventing a fiscal quarter.
   - For a close date without a year, choose the year giving the date nearest to today; use the supplied quarter context to resolve a tie, then prefer the future date if still tied.
   - List all year assignments in one assumption. Do not force an otherwise out-of-quarter date into the quarter.
   - Resolve ambiguous numeric dates using the user's stated convention; otherwise assume US month/day and state it.
   - A missing or invalid close date is not a year-less date: exclude the deal and list the gap.
4. Establish status without blocking the forecast.
   - Treat pasted pipeline deals as OPEN unless explicitly marked won, lost, signed, or closed.
   - State once: "Assumption: unmarked pipeline deals are open." Do not request status confirmation for those deals.
   - Exclude won, signed, lost, and closed deals from the open-pipeline forecast; state the supplied status as the reason.
   - For an unspecified "closed" outcome, list the outcome as missing but do not reopen the deal.
   - Do not assume won or signed amounts were deducted from remaining quota; require the manager to verify reconciliation.
5. Classify every deal and list every exclusion with its reason.
   - Include open deals with a valid amount, stated probability, and close date inside the inclusive quarter boundaries.
   - Keep overdue open deals included if their close dates are inside the quarter; flag risk without changing the dates.
   - Exclude out-of-quarter deals, showing their dates and the relevant boundary.
   - Exclude missing or invalid calculation inputs; retain those deals in the table and Data gaps.
   - Use quota currency for unmarked amounts only as a stated assumption.
   - Do not convert currencies. Show other-currency forecasts separately and exclude them from the quota-currency gap.
6. Calculate and show the arithmetic.
   - For each included deal: amount × (stated probability ÷ 100) = weighted value.
   - Show the addition of weighted values and a definite numeric total in each applicable currency.
   - Show remaining quota − quota-currency weighted forecast = gap.
   - With quota, amounts, and probabilities supplied, never label the figures "unavailable," "not calculable," or "conditional" because status or a close-date year was unstated.
   - If records are excluded for missing inputs, show the definite total of eligible records and identify its scope; do not present it as a complete-pipeline estimate.
   - If no records qualify, show 0 and the exclusion reasons. Missing probabilities are not zero probabilities.
   - A negative gap means weighted coverage above remaining quota, not assured attainment.
   - If quota remains missing after the single request, show the forecast and "Gap: remaining quota [NOT PROVIDED] − [forecast]"; never invent quota.
7. Screen every open deal, including excluded deals, using all six rules.
   - R1 Past close date: close date < today while not signed/won; show both dates.
   - R2 Stale activity: today − last activity > 21 calendar days; show the day count. Exactly 21 days does not trigger it.
   - R3 No next step: neither the next-step field nor notes records a specific next action; state "no next step recorded," not that no action exists.
   - R4 Champion/sponsor left: the record explicitly says the champion or sponsor departed; cite the de-identified supporting wording. Do not infer departure from a role change.
   - R5 Stage versus close-date mismatch: apply supplied team criteria and show the criterion, stage, and days to close. If none are supplied, report "R5 not assessed: criteria missing" and request them in Data gaps.
   - R6 Single-threaded: exactly one distinct contact/stakeholder is recorded across contact fields and notes. Always flag this as a risk, even if the deal is otherwise healthy.
   - Count a person only once when the record explicitly links their label and role; do not invent identities or assume two people with the same role are one.
   - If contact identity/count is ambiguous, flag R6 when only one distinct person is established and list the ambiguity; with no contacts recorded, report R6 not assessed.
   - For every other unassessable check, identify the missing or invalid field and affected rule. Missing activity alone does not prove staleness.
8. Write exactly one specific, open-ended coaching question per flagged deal.
   - Anchor it to recorded facts and prioritize the main risk if several rules trigger.
   - Questions may seek a manager's proposed action; never present an unrecorded contact or action as established.
9. List missing, invalid, or conflicting inputs under Data gaps.
   - Identify the affected deal or review input and calculation/check, with a focused clarification question.
   - Do not repeat coaching questions here. Defaults explicitly permitted above are assumptions, not invented deal facts.
10. Produce the five output sections in order.
    - Mark empty sections "None"; retain all deals and exclusion reasons.
    - Label the review a management estimate, not financial reporting.
    - If AI-generated voice follow-up is proposed, add the US limitation and exact citation from Hard limits to Forecast summary. Do not initiate calls.

## Output format

```markdown
## Forecast summary
Management estimate for review, not financial reporting.
- Quarter: [start–end] | Today: [date] | Quota currency: [currency]
- Weighted forecast: [weighted value] + […] = [total]
- Gap: [remaining quota] − [forecast] = [gap]
- Scope: [included/excluded counts; incomplete-record exclusions; other-currency totals]
- Assumptions: [list each once below the figures]
## Deal table
| Deal | Status | Amount / currency | Stage / stated % | Close date | Eligibility / exclusion reason | Weighted arithmetic | Last activity | Next step | Anonymous contacts / roles |
|---|---|---|---|---|---|---|---|---|---|
[Each deal; use NOT PROVIDED for missing fields; identify duplicate handling.]
## Risk flags
- [Deal — R# — triggering rule and supporting facts/arithmetic]
- [Unassessed checks and reasons, or None]
## Coaching questions
- [Flagged deal]: [exactly one specific question]
## Data gaps
- [Deal/input — missing, invalid, or conflicting item — affected check — clarification question]
```

## Hard limits

- Never invent deal data, probabilities, contacts, commitments, next steps, or risk thresholds.
- Never change a close date to fit the quarter or include an out-of-quarter deal.
- Never withhold supported forecast and gap figures because an unmarked deal lacks status or a close date lacks a year; apply the stated defaults.
- Never manufacture a missing quota or conceal exclusions behind a definite total.
- Forecast numbers are management estimates, not financial reporting or booked revenue.
- The responsible sales manager must verify CRM accuracy, arithmetic, exclusions, quarter boundaries, date assumptions, currency handling, risk criteria, and remaining-quota reconciliation before use.
- CRM data is personal data of contacts: paste only what is needed, de-identify contacts while preserving distinct counts, and use only organization-approved tools for that data.
- US: if follow-up uses AI-generated voice calls, the FCC's 2024 Declaratory Ruling (FCC-24-17) confirms the TCPA applies. The responsible professional, with qualified counsel or compliance as appropriate, must verify applicable requirements before calls.
- FCC Declaratory Ruling FCC-24-17 — the TCPA applies to AI-generated voices in calls — https://docs.fcc.gov/public/attachments/FCC-24-17A1.pdf (February 2024; checked 2026-10-19)
- For UK/AU use, do not claim local calling or privacy rules; the responsible professional must verify local requirements with qualified counsel or compliance.
- Before sharing or acting, see references/checklist.md.

## Example

Fictional input:
```text
Quarter ends 2026-12-31; today 2026-10-19; remaining quota USD 200,000. R5 criterion: Discovery with 0–14 days to close.
Example A: USD 100,000; Proposal 50%; close Nov 30; activity 2026-10-14; next: pricing call; contacts: A1 CFO, A2 IT lead.
Sample B: USD 80,000; Negotiation 75%; close 2026-10-10; activity 2026-09-20; next: none; contact B1 VP Ops; notes: sponsor B1 left.
Sample C: USD 60,000; Discovery 25%; close Jan 15; activity 2026-10-16; next: demo; contacts: C1 buyer, C2 CTO.
```

Abbreviated output:
```markdown
## Forecast summary
Management estimate, not financial reporting. Weighted forecast: USD 50,000 + 60,000 = 110,000. Gap: USD 200,000 − 110,000 = 90,000.
Assumptions: quarter 2026-10-01–2026-12-31; unmarked deals open; nearest-year dates: Nov 30 → 2026-11-30, Jan 15 → 2027-01-15.
## Deal table
Example A — included — USD 100,000 × (50 ÷ 100) = 50,000.
Sample B — included, overdue within quarter — USD 80,000 × (75 ÷ 100) = 60,000.
Sample C — excluded: 2027-01-15 is after quarter end 2026-12-31.
## Risk flags
Sample B — R1: Oct 10 < Oct 19; R2: 29 days > 21; R3: no next step recorded; R4: "sponsor B1 left"; R6: only B1 recorded.
Example A and Sample C: no flags; Sample C R5 does not trigger at 88 days to close.
## Coaching questions
Sample B: With your only recorded sponsor gone and the close date overdue, how will you establish whether a signing path still exists?
## Data gaps
Sample B — next step missing (R3): What next action, if any, is already agreed?
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

Weekly pipeline review — management estimate for review, not financial reporting.

FORECAST SUMMARY
  Quarter: 2027-01-01 – 2027-03-31 | Today: 2027-01-18 | Quota currency: USD
  Weighted forecast: 140,000 (Orion) + 36,000 (Bluefin) + 45,000 (Cedar) + 26,000 (Delta) = USD 247,000
  Gap: 400,000 − 247,000 = USD 153,000 still to cover
  Scope: 4 of 5 deals included; 1 excluded (Elm, out of quarter); 0 excluded for incomplete records; no other-currency amounts.
  Assumptions (each stated once):
    - Quarter start inferred as 2027-01-01 (three calendar months ending 2027-03-31) — verify against your fiscal calendar.
    - "$" treated as USD.
    - Unmarked pipeline deals are open. Cedar is explicitly "not signed," so it is open.
    - Nearest-year date assignments: Mar 15 → 2027-03-15; Feb 28 → 2027-02-28; Jan 10 → 2027-01-10; Mar 30 → 2027-03-30; activity dates Jan 15 → 2027-01-15, Dec 10 → 2026-12-10 (2027 would be a future date), Jan 9 → 2027-01-09, Jan 16 → 2027-01-16, Jan 17 → 2027-01-17.
    - No won/signed deals supplied; verify remaining quota already reflects any Q1 bookings.

DEAL TABLE
  1) Orion Example
     Status: open | USD 200,000 | Negotiation / 70% | Close 2027-03-15 (56 days out)
     Eligible: in quarter | 200,000 × (70 ÷ 100) = 140,000
     Last activity 2027-01-15 (3 days) | Next step: NOT PROVIDED | Contacts: O1 — CFO (only contact, per record)
  2) Bluefin Sample
     Status: open | USD 90,000 | Proposal / 40% | Close 2027-02-28 (41 days out)
     Eligible: in quarter | 90,000 × (40 ÷ 100) = 36,000
     Last activity 2026-12-10 (39 days) | Next step: NOT PROVIDED | Contacts: NOT PROVIDED
  3) Cedar Test Co
     Status: open, not signed | USD 50,000 | Commit / 90% | Close 2027-01-10 (8 days overdue)
     Eligible: in quarter, overdue — date not changed | 50,000 × (90 ÷ 100) = 45,000
     Last activity 2027-01-09 (9 days) | Next step: NOT PROVIDED (notes: "legal review pending") | Contacts: NOT PROVIDED
  4) Delta Example
     Status: open | USD 130,000 | Discovery / 20% | Close 2027-03-30 (71 days out)
     Eligible: in quarter | 130,000 × (20 ÷ 100) = 26,000
     Last activity 2027-01-16 (2 days) | Next step: NOT PROVIDED | Contacts: NOT PROVIDED
  5) Elm Sample
     Status: open | USD 75,000 | Proposal / 40% | Close 2027-04-20 (92 days out)
     EXCLUDED: 2027-04-20 is after quarter end 2027-03-31 | (would be 75,000 × 0.40 = 30,000 — not counted)
     Last activity 2027-01-17 (1 day) | Next step: NOT PROVIDED | Contacts: NOT PROVIDED
  No duplicate rows found.

RISK FLAGS
  - Orion — R6 single-threaded: record states the CFO is the only contact (1 distinct person). R3: no next step recorded.
  - Bluefin — R2 stale: 2027-01-18 − 2026-12-10 = 39 days > 21. R3: no next step recorded.
  - Cedar — R1 past close date: 2027-01-10 < 2027-01-18 and explicitly not signed. R3: notes say "legal review pending" but no specific next action, owner, or date is recorded.
  - Delta — R3: no next step recorded.
  - Elm (excluded, still screened) — R3: no next step recorded.
  Not triggered: R1 for Orion/Bluefin/Delta/Elm; R2 for Orion (3d), Cedar (9d), Delta (2d), Elm (1d); R4 for all (no departure wording in any record).
  Unassessed: R5 for all deals — no team stage/close-date criteria supplied. R6 for Bluefin, Cedar, Delta, Elm — no contacts recorded.

COACHING QUESTIONS
  - Orion: With USD 140,000 of weighted forecast resting on a single CFO relationship, who else on their side needs to be in the room before Mar 15, and how will you get there?
  - Bluefin: After 39 days with no logged activity on a Feb 28 close, what evidence do you have that this is still live, and what is the next concrete step?
  - Cedar: The close date passed eight days ago with legal review still pending — what specifically is legal waiting on, and what date are you now committing to?
  - Delta: What has to be true by the end of Discovery for a Mar 30 close to be realistic, and what is the agreed next step with the customer?
  - Elm: Given Apr 20 falls outside the quarter, what would need to happen for this to pull in, or is it correctly an early-Q2 deal?

DATA GAPS
  - Review input — R5 criteria missing (all deals): What minimum lead time by stage does your team use (e.g., Discovery needs ≥ N days to close)?
  - Review input — quarter start unconfirmed: Is Q1 2027-01-01 to 2027-03-31 in your fiscal calendar?
  - Review input — quota reconciliation: Does USD 400,000 already net out anything closed-won this quarter?
  - All five deals — next-step field missing (R3): What next action, if any, is already agreed on each?
  - Bluefin, Cedar, Delta, Elm — no contacts recorded (R6): How many distinct stakeholders are engaged on each, and in what roles?
  - Cedar — "legal review pending" (R1/R3): Is there a named owner and target date for legal completion?

Verify CRM accuracy, arithmetic, quarter boundaries, date assumptions, and quota reconciliation before using these figures.

