# Transcript — xl-en-xlookup-01 — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-20T12:33:02+00:00
- duration_s: 11.5
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: f7065f27ff0dadfa4c10d9fa2ee8cbe393e22a1f62a1ecc481f5ab5f7fd214a6

## Query (verbatim, from query file)

```text
You are an Excel helper for a small-business bookkeeper. Work ONLY from the two tables below.

1. Write ONE formula for cell D2 of the Invoices sheet that returns the client name for the client ID in B2 and can be filled down to D13. When the client ID is not in the Clients sheet, the cell must show the text "Not found" instead of an error.
2. List every invoice row (row number and invoice number) that will show "Not found".
3. Write a formula that returns the total amount of all invoices for client ID C-104, and state the result it returns on this data.
4. Explain in plain English, in at most 120 words, how the lookup formula works.
5. End with a short "Check before using" note for anything in the data a person should verify.

Do not invent client names, IDs or amounts that are not in the tables.

Sheet "Invoices" (A1:C13, header in row 1):
Row | A: Invoice | B: Client ID | C: Amount (USD)
2 | INV-1001 | C-101 | 1,250.00
3 | INV-1002 | C-104 | 980.50
4 | INV-1003 | C-102 | 4,350.00
5 | INV-1004 | C-101 | 615.25
6 | INV-1005 | C-105 | 2,200.00
7 | INV-1006 | C-118 | 1,740.00
8 | INV-1007 | C-104 | 3,125.75
9 | INV-1008 | C-103 | 890.00
10 | INV-1009 | C-105 | 1,505.40
11 | INV-1010 | C-102 | 760.00
12 | INV-1011 | C-104 | 2,049.75
13 | INV-1012 | C-103 | 1,310.60

Sheet "Clients" (A1:B6, header in row 1):
Row | A: Client ID | B: Client name
2 | C-101 | Northwind Example Bakery
3 | C-102 | Harbor Example Dental
4 | C-103 | Pine Example Studio
5 | C-104 | Summit Example Plumbing
6 | C-105 | Lakeside Example Vet

Column D of "Invoices" is empty and should hold the client name.
```

## Output (verbatim stdout, session metadata stripped)

1. D2 formula (fill down to D13):

=IFERROR(INDEX(Clients!B:B,MATCH(B2,Clients!A:A,0)),"Not found")

2. Rows showing "Not found":
Row 7 — INV-1006 (Client ID C-118, not present in Clients sheet)

No other rows are affected; all other client IDs exist in the Clients table.

3. Total for client C-104:

=SUMIF(Invoices!B:B,"C-104",Invoices!C:C)

Result on this data: 980.50 + 3,125.75 + 2,049.75 = 6,156.00

4. How it works:
MATCH searches column A of the Clients sheet for the client ID in B2 and returns its row position. INDEX then uses that position to pull the matching name from column B of Clients. If MATCH can't find the ID (no match exists), it produces an error, and IFERROR catches that error and displays "Not found" instead of a broken formula.

5. Check before using:
- C-118 (row 7, INV-1006) has no matching entry in the Clients sheet — confirm whether this is a new client missing from the list or a typo for an existing ID (e.g., C-101–C-105).
- Verify Amount values are stored as numbers, not text, so SUMIF and any totals calculate correctly.

