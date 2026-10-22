# Transcript — law-en-nda-redline-01 — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:41:32+00:00
- duration_s: 36.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 8894fc130eb58746538100a2cef93f7d94f5d67177d8bf94525204a39d0197b8

## Query (verbatim, from query file)

```text
You are assisting counsel for the party named in the playbook. Review the NDA clauses below against the playbook.
Output a table: Clause | Issue | Risk (High/Med/Low) | Proposed replacement language.
Then list anything missing from the NDA that the playbook requires.
Keep proposed language concise and consistent with the playbook. Do not assume facts; flag items requiring the supervising attorney's decision.
Material:
Our client: Example Robotics Inc. (fictional), disclosing and receiving party (mutual NDA). Purpose: evaluating a joint pilot.
Counterparty draft:
§2 Confidential Information means information marked "Confidential" at the time of disclosure.
§4 Term: obligations survive for 1 year after disclosure.
§6 Remedies: each party's total liability under this Agreement shall not exceed $5,000.
§7 Residuals: Receiving Party may use any information retained in the unaided memory of its personnel.
§9 Governing law: State of Delaware.
Playbook (client positions): oral and visual disclosures covered if summarized in writing within 30 days; term 3 years and trade secrets protected as long as they remain trade secrets; no liability cap for breach of confidentiality; no residuals clause; injunctive relief must be available; governing law Delaware is acceptable; must include return/destruction of information on request.
```

## Output (verbatim stdout, session metadata stripped)

CLAUSE-BY-CLAUSE REVIEW (counterparty draft vs. Example Robotics playbook)

1. §2 — Definition of Confidential Information
Issue: Limited to information marked "Confidential" at time of disclosure. No mechanism for oral/visual disclosures, which are common in pilot evaluations (demos, site visits, calls).
Risk: High — most practical disclosures in a pilot (demos, verbal technical discussions) would fall outside protection entirely.
Proposed replacement:
"Confidential Information means any information disclosed by either party, in written, oral, visual, or other tangible or intangible form, that is either (a) marked or identified as confidential at the time of disclosure, or (b) if disclosed orally or visually, is summarized in a writing that identifies it as confidential and is delivered to the Receiving Party within thirty (30) days of disclosure."

2. §4 — Term
Issue: Survival capped at 1 year, with no carve-out for trade secrets.
Risk: High — confidentiality obligations lapse well before the value of the information (and legal protection) would normally expire.
Proposed replacement:
"The obligations of confidentiality set forth herein shall survive for three (3) years from the date of disclosure of the applicable Confidential Information; provided, however, that with respect to any information that constitutes a trade secret under applicable law, such obligations shall continue for as long as the information remains a trade secret."

3. §6 — Remedies / Liability Cap
Issue: Blanket $5,000 cap on total liability, which would apply to confidentiality breaches. No express availability of injunctive relief.
Risk: High — a $5,000 cap is nominal and would make the NDA unenforceable as a practical deterrent; absence of injunctive relief language weakens ability to stop ongoing misuse.
Proposed replacement:
"The limitation of liability set forth in this Section shall not apply to, and there shall be no limitation on, either party's liability arising from a breach of its confidentiality obligations under this Agreement. Each party acknowledges that a breach of such obligations may cause irreparable harm for which monetary damages alone would be inadequate, and accordingly the non-breaching party shall be entitled to seek injunctive relief and specific performance, without the necessity of posting a bond, in addition to any other remedies available at law or in equity."

4. §7 — Residuals
Issue: Permits the Receiving Party to use information retained in unaided memory, regardless of confidentiality.
Risk: High — directly conflicts with playbook; a residuals clause substantially undermines the entire confidentiality obligation by permitting use/disclosure based on memory.
Proposed replacement: Delete Section 7 in its entirety. No residuals language should be included.
[Flag for supervising attorney: if counterparty refuses to delete and insists on some residuals carve-out, attorney should decide whether any narrowed fallback (e.g., excluding it from indemnified/trade-secret information) is acceptable — playbook as stated permits no residuals clause at all.]

5. §9 — Governing Law
Issue: None — Delaware is the playbook-approved jurisdiction.
Risk: Low — no change needed.

MISSING FROM THE NDA (playbook requirements not addressed anywhere in the draft)

- Return/Destruction of Information: No clause requiring return or destruction of Confidential Information on request or at termination. Needs to be added:
"Upon the Disclosing Party's written request, or upon expiration or termination of this Agreement, the Receiving Party shall promptly return or destroy (at the Disclosing Party's election) all Confidential Information in its possession or control, including all copies, and shall certify such destruction in writing upon request, except that Receiving Party may retain one archival copy solely for legal/compliance purposes, subject to the continuing confidentiality obligations herein."

- Injunctive Relief availability as a standalone right: addressed above by revising §6, but confirm it is not also conditioned or waived elsewhere in the agreement (e.g., no boilerplate "sole and exclusive remedy" language elsewhere that would contradict it).

ITEMS REQUIRING SUPERVISING ATTORNEY DECISION

1. Whether to seek outright deletion of the residuals clause (per playbook) or accept a narrowed version if counterparty resists — playbook language as given does not authorize any residuals carve-out, so this is a negotiation call, not a drafting call.
2. Whether the $5,000 liability cap should be removed only for confidentiality breaches (as drafted above) or whether client wants to negotiate the cap's applicability to other provisions of the agreement (e.g., indemnification, IP issues) — playbook only specifies "no cap for breach of confidentiality," so the cap's treatment elsewhere is undecided and needs confirmation.
3. Mechanics of the 30-day written-summary requirement (who is responsible for creating/sending the summary, format, and consequence of late summary) are not specified in the playbook beyond the 30-day requirement — attorney should confirm the drafted mechanism is acceptable or wants additional specificity (e.g., deemed-waiver language if the 30-day deadline is missed).

