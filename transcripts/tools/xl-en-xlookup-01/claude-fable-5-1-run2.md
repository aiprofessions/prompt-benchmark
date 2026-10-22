# Transcript — xl-en-xlookup-01 — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T12:36:56+00:00
- duration_s: 20.4
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

1. Formula for Invoices!D2 (fill down to D13):

   =IFERROR(VLOOKUP(B2,Clients!$A$2:$B$6,2,FALSE),"Not found")

   If your Excel has XLOOKUP (Excel 2021 / Microsoft 365), this is equivalent and simpler:

   =XLOOKUP(B2,Clients!$A$2:$A$6,Clients!$B$2:$B$6,"Not found")

2. Rows that will show "Not found":

   Row 7, INV-1006 (client ID C-118 is not in the Clients sheet)

   That is the only one. All other IDs (C-101 to C-105) exist in Clients.

3. Total for client C-104:

   =SUMIF(Invoices!$B$2:$B$13,"C-104",Invoices!$C$2:$C$13)

   Result on this data: 6,156.00 (980.50 + 3,125.75 + 2,049.75, from INV-1002, INV-1007 and INV-1011).

4. How the lookup works:

   VLOOKUP takes the client ID in B2 and searches for it in the first column of the Clients table (A2:B6). FALSE tells it to require an exact match, not a close one. When it finds the ID, it returns the value from the 2nd column of that table, which is the client name. The dollar signs lock the table reference so it does not shift when you fill the formula down; B2 is not locked, so each row looks up its own ID. If the ID is missing, VLOOKUP produces an #N/A error; IFERROR catches that and shows "Not found" instead. XLOOKUP does the same job with a built-in "not found" argument.

5. Check before using:

   - C-118 on INV-1006: either a typo for an existing ID or a new client missing from the Clients sheet. Resolve it rather than leaving "Not found" in the books.
   - The formulas reference Clients!A2:B6 and Invoices rows 2-13 exactly. If either sheet grows, extend the ranges (or convert both to Excel Tables).
   - Confirm the Amount column holds real numbers, not text with commas, or SUMIF will return 0 or undercount.
   - Lookup IDs must match exactly, including no trailing spaces and the same hyphen character, in both sheets.

