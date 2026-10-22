# Transcript — xl-en-xlookup-01 — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-20T12:33:02+00:00
- duration_s: 19.9
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

1. Formula for D2 (fill down to D13)

   =XLOOKUP(B2, Clients!$A$2:$A$6, Clients!$B$2:$B$6, "Not found")

2. Rows that will show "Not found"

   Row 7, INV-1006 (client ID C-118, which is not in the Clients sheet)

   No other rows. All other IDs (C-101 to C-105) are in Clients.

3. Total for client C-104

   =SUMIF(B2:B13, "C-104", C2:C13)

   Result: 6,156.00
   (INV-1002 980.50 + INV-1007 3,125.75 + INV-1011 2,049.75)

4. How the lookup works (plain English)

   The formula takes the client ID in B2 and searches for it in column A of the Clients sheet. When it finds a match, it returns the client name from column B on the same row. If the ID isn't in the list, it shows "Not found" instead of an error. The dollar signs lock the Clients ranges in place, so when you fill the formula down, only B2 changes (to B3, B4, and so on) while the lookup list stays the same. XLOOKUP looks for an exact match by default, so C-101 will never match C-110 or a similar-looking ID.

5. Check before using

   - C-118 (INV-1006, 1,740.00) has no client record. Check whether it's a typo for an existing ID or a new client who needs to be added to the Clients sheet.
   - XLOOKUP needs Excel 365 or 2021 or later. For older versions, use:
     =IFERROR(VLOOKUP(B2, Clients!$A$2:$B$6, 2, FALSE), "Not found")
     Note that this version also hides any other errors as "Not found."
   - Confirm the amounts in column C are stored as numbers, not text, or SUMIF will skip them.
   - Check the client IDs for extra spaces or different dash characters. An ID that looks correct but contains either one will show "Not found."
   - If you add clients below row 6, extend the $A$2:$A$6 and $B$2:$B$6 ranges, or convert the Clients list to an Excel Table.

