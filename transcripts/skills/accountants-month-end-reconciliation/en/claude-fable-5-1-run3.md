# Transcript — skill accountants-month-end-reconciliation [en] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:35:40+00:00
- duration_s: 37.3
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

RECONCILIATION SUMMARY
Bank balance: 42,315.75; GL cash: 39,112.10
Adjusted bank: 40,280.50; adjusted books: 40,280.50 (provisional — includes unidentified ACH credit held in suspense)
Status: Arithmetic agrees; reconciliation provisional.

BANK SIDE
Starting statement balance: 42,315.75
Check #2214 (Sample Freight) — bank-side timing, outstanding check recorded in GL Sept 29, not yet cleared: 42,315.75 − 3,400.00 = 38,915.75
Check #2219 (Example Janitorial) — bank-side timing, outstanding check recorded in GL Sept 30, not yet cleared: 38,915.75 − 615.25 = 38,300.50
Night-drop deposit — bank-side timing, deposit in transit recorded in GL Sept 30, not on statement: 38,300.50 + 1,980.00 = 40,280.50
Adjusted bank balance: 40,280.50
Bank-error adjustments: none identified.

BOOK SIDE
Starting GL cash balance: 39,112.10
Interest credited — book-side credit, on statement, absent from GL: 39,112.10 + 8.40 = 39,120.50
Bank service fee — book-side debit, on statement, absent from GL: 39,120.50 − 45.00 = 39,075.50
Check #2201 (supplier) — book-side recording error, payment:
    Recorded payment 927.00; supported correct payment 972.00 (cleared amount and supplier invoice agree)
    Cash adjustment = recorded − correct = 927.00 − 972.00 = −45.00
    Payment was recorded too LOW; book cash DECREASES by 45.00
    39,075.50 − 45.00 = 39,030.50
ACH CREDIT REF 88231 (Sept 24) — unidentified bank credit; amount, credit direction, and absence from GL established; source and purpose unknown. Provisional suspense adjustment pending evidence:
    39,030.50 + 1,250.00 = 40,280.50 (PROVISIONAL)
Adjusted book balance: 40,280.50 (provisional pending resolution of ACH credit)

DIFFERENCE
40,280.50 − 40,280.50 = 0.00
Status: Arithmetic agrees; reconciliation provisional. The zero difference depends on a 1,250.00 suspense adjustment whose source is unknown; it does not establish that the ACH credit belongs in this account or what it represents.
Unresolved items and missing inputs:
    ACH CREDIT REF 88231, 1,250.00 — source, payer, and purpose unidentified; held in suspense, not recognized as revenue.
    Check #2201 — original GL entry and offsetting account not supplied; correction account marked "confirm" below.
Follow-up:
    Obtain bank ACH detail (originator name, company ID, addenda) for REF 88231; match to open A/R, customer remittances, refunds, or intercompany transfers; confirm the credit was not posted to a different GL account.
    Confirm checks #2214 and #2219 clear on the October statement; if either remains outstanding beyond a normal window, investigate.
    Confirm the 1,980.00 night-drop deposit appears on the October statement at the same amount and date; verify deposit slip and cash receipts log.
    Pull the original GL posting for check #2201 to confirm the 927.00 amount, the expense/payable account charged, and whether the 927/972 difference is a transposition in the check register or in the invoice posting.
    Confirm the 45.00 fee and 8.40 interest are September-dated on the statement and were not posted in the GL under a different account or date (cutoff).
    Confirm no additional unmatched items exist beyond the seven listed.

PROPOSED JOURNAL ENTRIES (book side only — not posted)
JE-1 / Interest credited
    Dr Cash — operating (4417)            8.40
        Cr Interest income                        8.40
    Debits 8.40 = Credits 8.40. Evidence: statement interest line — supplied.

JE-2 / Bank service fee
    Dr Bank fees expense                 45.00
        Cr Cash — operating (4417)               45.00
    Debits 45.00 = Credits 45.00. Evidence: statement fee line — supplied.

JE-3 / Check #2201 recording correction
    Dr [original offsetting account — confirm]   45.00
        Cr Cash — operating (4417)                       45.00
    Debits 45.00 = Credits 45.00. Corrects payment recorded at 927.00 to supported 972.00. Evidence: cleared check amount and supplier invoice (972.00) — supplied as stated; original GL entry — missing.

JE-4 / ACH CREDIT REF 88231 — PENDING EVIDENCE — provisional; not revenue or expense
    Dr Cash — operating (4417)        1,250.00
        Cr Unidentified receipts / suspense          1,250.00
    Debits 1,250.00 = Credits 1,250.00. Do not post without professional approval; reclassify from suspense only when the source is documented.

No entries proposed for checks #2214, #2219, or the night-drop deposit (timing items). No bank errors identified.

EVIDENCE NEEDED BEFORE POSTING
JE-1: September statement showing 8.40 interest credit — supplied; confirm interest income account and that no prior posting exists.
JE-2: September statement showing 45.00 service fee — supplied; confirm expense account and that no prior posting exists.
JE-3: Original GL entry for check #2201 (amount, date, account charged) — missing; check image or cleared-check detail at 972.00 — supplied per input, retain copy; supplier invoice at 972.00 — supplied per input, retain copy; confirm the offsetting account (A/P or expense) before replacing the placeholder.
JE-4: Bank ACH transaction detail for REF 88231 (originator, company ID, addenda) — missing; remittance advice or customer/counterparty correspondence — missing; confirmation the credit is not already recorded elsewhere in the GL — missing. Final account treatment to be determined by the responsible accountant once source is identified.

REVIEW AND SIGN-OFF
Prepared by: __________________  Date: __________________
Reviewed by (responsible accountant): __________________  Date: __________________

Notes for the file: figures used as supplied, no rounding introduced; account number masked to last four digits throughout. Before signing, the responsible accountant should verify account/date/currency alignment, completeness of the unmatched-item list, cutoff, the Check #2201 original entry, and resolution of the ACH credit, and should run the pre-sign checklist in the skill's references/checklist.md.

