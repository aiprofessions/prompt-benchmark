# Transcript — skill accountants-month-end-reconciliation [en] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:58:56+00:00
- duration_s: 31.8
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

BANK RECONCILIATION MEMO - Birch Example Co. - account ending 4417 - September 30, 2026
Currency: USD

RECONCILIATION SUMMARY
  Bank balance: 42,315.75; GL cash: 39,112.10
  Adjusted bank: 40,280.50; adjusted books: 40,280.50 (provisional; includes 1,250.00 suspense)
  Status: Arithmetic agrees; reconciliation provisional.

BANK SIDE
  Starting statement balance: 42,315.75
  Check #2214, Sample Freight. Bank-side timing: outstanding check, written Sept 29.
    42,315.75 - 3,400.00 = 38,915.75
  Check #2219, Example Janitorial. Bank-side timing: outstanding check, written Sept 30.
    38,915.75 - 615.25 = 38,300.50
  Night-drop deposit, booked Sept 30. Bank-side timing: deposit in transit.
    38,300.50 + 1,980.00 = 40,280.50
  Adjusted bank balance: 40,280.50
  Bank errors identified: none.

BOOK SIDE
  Starting GL cash balance: 39,112.10
  Bank service fee. Book-side fee on the statement, not in the GL.
    39,112.10 - 45.00 = 39,067.10
  Interest credit. Book-side interest on the statement, not in the GL.
    39,067.10 + 8.40 = 39,075.50
  Check #2201, supplier. Book-side recording error (payment):
    Recorded 927.00. Correct 972.00 per the invoice and the cleared amount.
    927.00 - 972.00 = -45.00
    The payment was recorded too low, so book cash decreases by 45.00.
    39,075.50 - 45.00 = 39,030.50
  ACH CREDIT REF 88231, Sept 24. Unidentified bank credit on the statement, not in the GL.
    PROVISIONAL suspense adjustment, pending evidence.
    39,030.50 + 1,250.00 = 40,280.50
  Adjusted book balance: 40,280.50 (provisional)

DIFFERENCE
  40,280.50 - 40,280.50 = 0.00
  Status: Arithmetic agrees; reconciliation provisional.
  Unresolved items and missing inputs:
    ACH CREDIT REF 88231, 1,250.00. Source and purpose are unknown. It is held in suspense and is not revenue.
    Check #2201: the original GL entry and its offsetting account were not supplied.
    You described the supplier invoice and the bank statement but did not attach them.
  Follow-up:
    Confirm checks #2214 and #2219 and the 1,980.00 deposit are posted in the September GL.
    Trace all three to clearing on the October statement.
    Verify the night-drop deposit was physically made on or before Sept 30 (cutoff).
    Obtain ACH remitter detail for REF 88231 from the bank.
    Match REF 88231 against open receivables, customer remittances, refunds, and transfers.
    Confirm the 45.00 fee and the 45.00 check #2201 correction are distinct items, not one difference counted twice.

PROPOSED JOURNAL ENTRIES (BOOK SIDE ONLY - NOT POSTED)
  JE-1 (bank service fee)
    Dr  Bank service fees [expense account - confirm]       45.00
    Cr  Cash - operating ...4417                                       45.00
    Debits = credits = 45.00. Evidence: statement fee line (missing).
  JE-2 (interest credit)
    Dr  Cash - operating ...4417                             8.40
    Cr  Interest income [account - confirm]                             8.40
    Debits = credits = 8.40. Evidence: statement interest line (missing).
  JE-3 (check #2201 correction)
    Dr  [original offsetting account - confirm]             45.00
    Cr  Cash - operating ...4417                                       45.00
    Debits = credits = 45.00. Evidence: original entry, invoice, cleared item (missing).
  JE-4 (ACH CREDIT REF 88231)
    PENDING EVIDENCE - provisional; not revenue or expense.
    Dr  Cash - operating ...4417                         1,250.00
    Cr  Suspense - unidentified receipts                            1,250.00
    Debits = credits = 1,250.00. Evidence: bank ACH detail and source documents (missing).
  Combined total: debits 1,348.40 = credits 1,348.40.
  Net cash effect: +1,168.40 (39,112.10 + 1,168.40 = 40,280.50).
  No entries for timing items (#2214, #2219, deposit in transit) or bank errors.

EVIDENCE NEEDED BEFORE POSTING
  JE-1: September statement showing the 45.00 fee (missing). Confirm the fee is absent from the GL and confirm the expense account.
  JE-2: September statement showing the 8.40 interest credit (missing). Confirm it is absent from the GL and confirm the income account.
  JE-3: Original GL entry for #2201 (missing). Supplier invoice for 972.00 (described, not supplied). Bank image or cleared-item detail for 972.00 (missing). Confirm the offsetting account, e.g. AP or expense.
  JE-4: Bank ACH detail showing the originator and addenda (missing). Source documentation such as a remittance advice, contract, or transfer record (missing). Determine the final treatment and reclass out of suspense once it is identified.

REVIEW AND SIGN-OFF
  Prepared by: __________________  Date: __________________
  Reviewed by (responsible accountant): __________________  Date: __________________

Notes:
  A zero difference does not make this reconciliation complete. The responsible accountant must verify classifications, cutoff, evidence, and the suspense item before any posting or sign-off.
  Before relying on or signing the memo, see references/checklist.md.

