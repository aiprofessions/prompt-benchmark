# Transcript — skill accountants-month-end-reconciliation [en] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:11:23+00:00
- duration_s: 58.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e5af919d713a29dad248b394abf604f5c0e8f1cba0dfebeb70369a19f8a16ac0
- skill_sha256: 4dcfbee80358bd21532840700dddfa91551e9b14596a855ed3e861a610296c5b

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: accountants-month-end-reconciliation
description: "Use when a user pastes bank and GL cash balances and unmatched items to receive a two-sided reconciliation memo with proposed book-side entries."
---

# Month-End Bank Reconciliation Memo

## What it does

Builds a client-file reconciliation memo comparing adjusted bank cash with adjusted general-ledger (GL) cash, with arithmetic shown line by line. Classifies unmatched items and proposes book-side entries with supporting evidence requirements. Leaves preparation and review sign-off to the responsible humans. Uses US terminology without claiming UK or Australian requirements.

## Inputs it expects

- Entity placeholder, account identifier (last four digits only), period-end date, and currency.
- Bank statement ending balance and GL cash balance for that account and date.
- Every unmatched item: reference, date, description, amount, and whether it appears only on the statement, only in the books, or in both at different amounts.
- For recording errors: payment or receipt, recorded amount, supported correct amount, and original entry or offsetting account if known.
- Available supporting records and any known bank errors, duplicates, or cutoff concerns.

Ask once for all missing or conflicting inputs together. If proceeding without them, list them under Difference; never infer figures, dates, currency, or unsupported classifications. If a starting balance or necessary item amount is missing, show only calculable subtotals and mark the reconciliation incomplete.

## Procedure

1. Apply the privacy rules before requesting more data. Mask every account number to at most its last four digits in all output, including quoted references.
2. Preserve supplied figures and precision; introduce only calculated results or item counts. Confirm that both balances cover the same account, date, and currency; flag mismatches rather than combining them.
3. Inventory every unmatched item once using its supplied reference or a generated item label. Flag possible duplicates for confirmation; do not silently remove or count them twice.
4. Assign each item a classification and reason supported by the inputs:
   - Bank-side timing: recorded outstanding checks/transfers out decrease bank cash; recorded deposits/transfers in transit increase bank cash. Confirm that the books already contain the item.
   - Book-side: supported fees, interest, returned items, unrecorded transactions, and recording errors requiring changes to the books.
   - Unidentified bank debit/credit: unresolved source or purpose; hold as unidentified/suspense pending evidence, never as established revenue or expense.
   - Other unresolved items, including possible bank errors: state what is unknown and request evidence. Do not force them into a timing or book-side category.
5. Bank side: show statement balance, then each supported adjustment as a separate addition or subtraction with a running total. Label the final total adjusted bank balance; separately identify any supported bank-error adjustment and propose no book entry for it.
6. Compute each recording correction using the supported correct amount:
   - Payment: cash adjustment = recorded payment minus correct payment.
   - Receipt/deposit: cash adjustment = correct receipt minus recorded receipt.
   - Show the subtraction and signed result. A positive result INCREASES book cash; a negative result DECREASES book cash by its absolute amount.
   - Explicitly state whether the payment or receipt was recorded too high or too low. If the correct amount is unsupported, leave the correction unresolved.
7. Book side: start with GL cash; add supported interest/credits, subtract supported fees/debits, and apply each signed recording correction. Show one arithmetic line and running total per item.
8. For an unidentified bank item, use a provisional cash/suspense adjustment only if its amount, debit/credit direction, and absence from the GL are established. Label the adjustment and resulting total provisional, pending evidence; otherwise list it unresolved without adjusting cash.
9. Compute Difference = adjusted bank balance minus adjusted book balance and show the subtraction. Report any nonzero amount, with sign, as Unexplained difference; never add a plug or change a classification to eliminate it.
10. If the difference is zero but evidence or classification remains unresolved, say "Arithmetic agrees; reconciliation provisional." Use "Reconciled — subject to human review" only when the inputs are complete and no unresolved items remain. If essential figures are missing, say "Incomplete — difference not determinable."
11. Propose journal entries only for book-side adjustments, with linked item references, debit/credit amounts, and equal entry totals. Propose none for timing items or bank errors. Use "[original offsetting account — confirm]" when the correction account is unknown, not a guessed account.
12. Label any suspense entry "PENDING EVIDENCE — provisional; not revenue or expense." Never treat an unidentified transaction's source or final accounting treatment as fact.
13. For each proposed entry, list the specific evidence needed before posting and whether supplied or missing. Require the original GL entry and payment/receipt evidence for corrections, and bank detail plus source documentation for unidentified items.
14. Check that every unmatched item appears once as an adjustment or unresolved item; independently recompute all totals and confirm entry balance. List targeted follow-up checks without presenting guesses as findings.
15. Produce the sections below in order. Leave all preparer/reviewer names and sign-off dates blank; the responsible accountant, not the model, signs.

## Output format

```markdown
# Bank Reconciliation Memo — [Entity] — account ending [last four] — [period end]
Currency: [supplied currency or missing]

## Reconciliation summary
Bank balance: [starting]; GL cash: [starting]
Adjusted bank: [amount]; adjusted books: [amount; provisional if applicable]
Status: [Reconciled — subject to human review / Provisional / Unexplained difference / Incomplete]

## Bank side
Starting statement balance: [amount]
[Item reference — classification and reason]: [prior total] +/− [amount] = [running total]
[Repeat separately for every bank-side adjustment.]
Adjusted bank balance: [amount or not determinable]

## Book side
Starting GL cash balance: [amount]
[Item reference — classification and reason]: [prior total] +/− [amount] = [running total]
[For errors: recorded and correct amounts, subtraction, signed cash adjustment, direction.]
[For suspense: identify provisional adjustment pending evidence.]
Adjusted book balance: [amount or not determinable; provisional if applicable]

## Difference
[Adjusted bank] − [adjusted books] = [signed difference or not determinable]
[Status; label any nonzero difference Unexplained difference.]
Unresolved items and missing inputs: [each item, amount if known, reason not adjusted]
Follow-up: [specific checks; no unsupported findings]

## Proposed journal entries (book side only)
[JE reference / item reference / account / debit / credit / evidence status]
[Show both sides and equal debit/credit totals for each entry.]
[Any suspense entry: PENDING EVIDENCE — provisional; not revenue or expense.]
No entries for timing items or bank errors.

## Evidence needed before posting
[JE reference]: [specific documents; supplied/missing; account treatment to confirm]

## Review and sign-off
Prepared by: __________________  Date: __________________
Reviewed by (responsible accountant): __________________  Date: __________________
```

## Hard limits

- Never invent source figures, account details, dates, classifications, or supporting evidence. Calculated results are permitted; unsupported assumptions are not.
- Never force agreement, conceal unresolved items, or propose entries for timing items or bank errors. Do not post entries or imply that proposals have been posted.
- Never treat unidentified credits/debits as established revenue/expense. Suspense proposals remain pending evidence and professional approval.
- The responsible accountant, or licensed professional where required, must verify account/date/currency alignment, completeness, cutoff, classifications, arithmetic, original entries, offsetting accounts, evidence, and suspense resolution before posting or signing.
- The accountant, not the model, signs the reconciliation. A zero difference alone does not establish that the reconciliation is complete or correct.
- Privacy: de-identify client data before pasting, use placeholders and at most the last four account digits, and use only tools approved by the firm for the data involved. Do not request unnecessary identifying information.
- Client tax-return information is protected. Before pasting it into any AI tool, the user must check IRC §7216 consent rules and satisfy applicable requirements; de-identification or firm approval alone does not establish compliance.
- The IRS OPR published responsible-AI guidelines for tax practice. The responsible professional must review applicable guidance and verify the output rather than treating model output as authority.
- US-first method only: UK/AU practitioners must verify local confidentiality, professional, and posting requirements with their responsible professional or professional body; the US sources do not establish local rules.
- Before using or signing the memo, see references/checklist.md.

Official sources:
- IRS — Section 7216 Information Center (disclosure/use of tax return information) — https://www.irs.gov/tax-professionals/section-7216-information-center (page checked 2026-10-19)
- IRS Office of Professional Responsibility — Issue 2026-19, Introductory guidelines for responsible AI use in federal tax practice — https://www.irs.gov/pub/opr-taxpros/issue-number-2026-19-introductory-guidelines-for-responsible-ai-use-in-federal-tax-practice.pdf (2026; checked 2026-10-19)

## Example

Input (fictional):
```text
Sample Entity; account ending 1234; period ended September 30; USD.
Bank ending balance 1,000.00; GL cash balance 920.00; all unmatched items below.
Check A: 100.00 recorded in GL, outstanding at period end.
Fee B: 20.00 on bank statement, absent from GL; statement supplied.
```

Output (abbreviated):
```text
Reconciliation summary
Adjusted bank and books: USD 900.00; Reconciled — subject to human review.
Bank side
1,000.00 − 100.00 (Check A, bank-side timing) = 900.00.
Book side
920.00 − 20.00 (Fee B, book-side fee) = 900.00.
Difference
900.00 − 900.00 = 0.00; missing inputs/unresolved items: none.
Proposed journal entries (book side only)
JE B: Dr Bank fees 20.00 / Cr Cash 20.00; debits = credits = 20.00; no timing entry.
Evidence needed before posting
JE B: supplied statement fee line; reviewer must verify GL omission and expense account.
Review and sign-off
Prepared by: __________ Date: __________
Reviewed by (responsible accountant): __________ Date: __________
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Please prepare the September month-end bank reconciliation memo for the client file.
Client: Birch Example Co. (fictional). Period ending September 30, 2026. Operating account ending 4417.
Bank statement ending balance: $42,315.75
General ledger cash balance: $39,112.10
Unmatched items:
- Check #2214 to Sample Freight, $3,400.00, written Sept 29, not yet on the bank statement.
- Check #2219 to Example Janitorial, $615.25, written Sept 30, not yet on the bank statement.
- Deposit of $1,980.00 recorded in the books Sept 30, not on the statement (night drop).
- Bank service fee $45.00 on the statement, not in the books.
- Interest credited $8.40, not in the books.
- Check #2201 to a supplier recorded in the books as $927.00; it cleared the bank as $972.00; the supplier invoice says $972.00.
- ACH credit of $1,250.00 on Sept 24, reference "ACH CREDIT REF 88231" — nobody knows what it is yet.
````

## Output (verbatim stdout, session metadata stripped)

Bank Reconciliation Memo — Birch Example Co. (fictional) — account ending 4417 — September 30, 2026
Currency: USD

## Reconciliation summary
Bank balance: $42,315.75; GL cash: $39,112.10
Adjusted bank: $40,280.50; adjusted books: $40,280.50 (provisional — see suspense item)
Status: Arithmetic agrees; reconciliation provisional.

## Bank side
Starting statement balance: $42,315.75

Check #2214 (Sample Freight, written 9/29) — bank-side timing, outstanding check; confirmed recorded in books, not yet cleared:
$42,315.75 − $3,400.00 = $38,915.75

Check #2219 (Example Janitorial, written 9/30) — bank-side timing, outstanding check; confirmed recorded in books, not yet cleared:
$38,915.75 − $615.25 = $38,300.50

Deposit, night drop, $1,980.00 (recorded in books 9/30) — bank-side timing, deposit in transit; confirmed recorded in books, not yet credited by bank:
$38,300.50 + $1,980.00 = $40,280.50

Adjusted bank balance: $40,280.50

No supported bank errors identified; no bank-side entry proposed for any item above.

## Book side
Starting GL cash balance: $39,112.10

Bank service fee $45.00 (on statement, not in books) — book-side fee:
$39,112.10 − $45.00 = $39,067.10

Interest credited $8.40 (not in books) — book-side interest:
$39,067.10 + $8.40 = $39,075.50

Check #2201 — recording error (payment). Recorded $927.00; supported correct amount $972.00 (per cleared-bank amount and supplier invoice).
Cash adjustment = recorded − correct = $927.00 − $972.00 = −$45.00.
Payment was recorded too LOW; book cash decreases by $45.00 (the check actually cleared for more than was booked).
$39,075.50 − $45.00 = $39,030.50

ACH credit $1,250.00, 9/24, ref "ACH CREDIT REF 88231" — unidentified bank credit. Treated as a provisional suspense adjustment to book cash on the working assumption that it is absent from the GL (it was listed as an unmatched/unrecognized item and its absence from the books has not been explicitly confirmed — see Difference section). Source and proper classification unknown.
$39,030.50 + $1,250.00 = $40,280.50 — PROVISIONAL, pending evidence.

Adjusted book balance: $40,280.50 (provisional — depends on confirming the ACH item's absence from the GL and its eventual classification)

## Difference
$40,280.50 (adjusted bank) − $40,280.50 (adjusted books) = $0.00
Arithmetic agrees; reconciliation provisional — the zero difference depends on an unconfirmed assumption (see below) and does not by itself establish the reconciliation is complete or correct.

Unresolved items and missing inputs:
- ACH credit $1,250.00 (ref 88231, 9/24): source and purpose unknown. Confirmation needed that this amount does not already appear anywhere in the GL (under this or another reference) before the suspense entry below can be relied upon. If it is later found to already be recorded, or if the amount/direction is not confirmed, this adjustment must be reversed and the item held unresolved instead.
- Check #2201: confirm that the original GL entry, the $927.00 recorded figure, and the $972.00 cleared/invoice amount all relate to the same transaction (no duplicate or unrelated check with a similar number).

Follow-up:
- Obtain bank item detail / remittance information for ACH ref 88231 (originator, purpose) and confirm it is not recorded anywhere in the GL under a different reference or date.
- Pull the original GL entry for check #2201 and confirm offsetting account (e.g., accounts payable, specific expense) before posting the correction.
- Confirm checks #2214 and #2219 and the night-drop deposit clear in the subsequent bank statement (standard cutoff check).
- Confirm no other transactions post to this account between the period-end date and statement cutoff that could affect the $1,250 coincidence noted above (the suspense amount exactly closes the gap left by the other items, which warrants a second look rather than being taken as confirmation).

## Proposed journal entries (book side only)

JE-1 (Bank service fee):
Dr Bank fees expense $45.00
Cr Cash $45.00
Debits = Credits = $45.00

JE-2 (Interest income):
Dr Cash $8.40
Cr Interest income $8.40
Debits = Credits = $8.40

JE-3 (Check #2201 correction — additional $45.00 of actual payment not yet recorded):
Dr [original offsetting account — confirm] $45.00
Cr Cash $45.00
Debits = Credits = $45.00

JE-4 (ACH credit, ref 88231) — PENDING EVIDENCE — provisional; not revenue or expense:
Dr Cash $1,250.00
Cr Suspense / unidentified deposits $1,250.00
Debits = Credits = $1,250.00

No entries proposed for checks #2214, #2219, or the night-drop deposit (bank-side timing items). No bank errors identified; no entries for bank errors.

## Evidence needed before posting

JE-1: Bank statement fee line — supplied. Confirm fee description/date and GL expense account.

JE-2: Bank statement interest line — supplied. Confirm GL interest income account.

JE-3: Original GL entry for check #2201 — missing. Supplier invoice supporting $972.00 — referenced but not attached; obtain copy. Confirm offsetting account (currently unknown) before posting.

JE-4: Bank detail/source documentation for ACH ref 88231 — missing. Must obtain originator information and confirm absence from GL before this entry can move from suspense to a final classification (revenue, liability, customer refund, etc. — not yet established).

## Review and sign-off
Prepared by: __________________  Date: __________________
Reviewed by (responsible accountant): __________________  Date: __________________

