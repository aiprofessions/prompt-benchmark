# Transcript — law-en-nda-redline-01 — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:11:30+00:00
- duration_s: 19.1
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

Clause | Issue | Risk | Proposed replacement language
---|---|---|---
§2 Confidential Information | Definition limited to information marked "Confidential" at time of disclosure. Excludes oral/visual disclosures entirely — playbook requires coverage if summarized in writing within 30 days. | High | "Confidential Information" means any non-public information disclosed by either party, whether in written, electronic, oral, or visual form, that is marked or identified as confidential at the time of disclosure, or, if disclosed orally or visually, is summarized in a writing identifying it as confidential and delivered to the Receiving Party within 30 days of disclosure.
§4 Term | Survival period of 1 year falls short of playbook's 3-year minimum, and contains no carve-out for trade secrets (which should survive as long as they remain trade secrets). | High | "The obligations of confidentiality under this Agreement shall survive for three (3) years from the date of disclosure; provided, that with respect to any Confidential Information that constitutes a trade secret under applicable law, such obligations shall survive for as long as such information remains a trade secret."
§6 Remedies | $5,000 liability cap conflicts with playbook's "no liability cap for breach of confidentiality" and omits injunctive relief, which playbook requires be expressly available. | High | "Nothing in this Agreement shall limit either party's liability for breach of its confidentiality obligations hereunder. Each party acknowledges that monetary damages may be an inadequate remedy for breach of this Agreement and agrees that the non-breaching party shall be entitled to seek injunctive relief and other equitable remedies, in addition to any other remedies available at law, without the necessity of posting bond."
§7 Residuals | Playbook prohibits any residuals clause; this provision would permit broad use of "unaided memory" information, undermining confidentiality protections. | High | Delete §7 in its entirety.
§9 Governing Law | Delaware is acceptable per playbook. | Low (none) | No change needed. Confirm whether venue/forum selection language should also be added — not addressed in counterparty draft; flag for attorney decision if desired.

Missing from the NDA (playbook requirements not addressed in counterparty draft):

1. Return/destruction of Confidential Information upon request or termination — no provision exists. Needs to be added, e.g.: "Upon the Disclosing Party's written request, the Receiving Party shall promptly return or destroy all Confidential Information and certify such destruction in writing, except that Receiving Party may retain one archival copy solely for legal compliance purposes, which shall remain subject to this Agreement's confidentiality obligations."

2. No carve-out confirming trade secrets survive indefinitely as trade secrets — should be folded into §4 as drafted above, but confirm with supervising attorney whether a separate standalone trade-secret clause is preferred over the integrated approach.

Items requiring supervising attorney's decision:

- Whether the 30-day written-summary mechanism for oral/visual disclosures should have any exceptions (e.g., disclosures made in group settings, demos during the pilot).
- Whether to add mutual indemnification or expense-shifting language for breach, since the liability cap is being removed — playbook doesn't specify whether a reciprocal fee-shifting clause is desired.
- Whether venue/jurisdiction (not just governing law) should be specified for Delaware, since §9 only addresses choice of law.
- Confirm no other counterparty-favorable terms exist in sections not provided (e.g., assignment, non-solicitation, or export control clauses) that may need playbook review.

