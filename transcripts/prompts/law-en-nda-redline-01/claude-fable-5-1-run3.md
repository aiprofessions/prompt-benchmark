# Transcript — law-en-nda-redline-01 — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:44:41+00:00
- duration_s: 27.9
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

Review of counterparty draft NDA vs. Example Robotics Inc. playbook (mutual NDA; purpose: joint pilot evaluation)

Clause | Issue | Risk | Proposed replacement language
--------------------------------------------------------------------------------------------------
§2 Definition | Covers only information marked "Confidential" at disclosure. Excludes oral/visual disclosures and anything unmarked; playbook requires oral/visual coverage with 30-day written summary. Pilot evaluation will involve demos and discussions. | High | "Confidential Information means all non-public information disclosed by a party, whether in writing, orally, visually, or by inspection, that is marked or identified as confidential at the time of disclosure or, if disclosed orally or visually, is identified as confidential at the time of disclosure and summarized in writing to the Receiving Party within thirty (30) days thereafter." [Attorney decision: whether to also push for a "reasonable person would understand to be confidential" catch-all, which is broader than the stated playbook position.]

§4 Term | 1-year survival, measured from disclosure; playbook requires 3 years, with trade secrets protected as long as they qualify as trade secrets. | High | "The Receiving Party's obligations under this Agreement shall survive for three (3) years following the expiration or termination of this Agreement; provided that, with respect to any Confidential Information that constitutes a trade secret under applicable law, such obligations shall continue for so long as such information remains a trade secret." [Attorney decision: playbook does not specify whether the 3 years runs from each disclosure or from termination of the Agreement; draft above uses termination. Confirm.]

§6 Remedies | $5,000 aggregate liability cap; playbook permits no cap for breach of confidentiality. Cap would effectively nullify remedies and is inconsistent with injunctive relief. Draft also lacks any injunctive relief provision (see Missing). | High | "Nothing in this Agreement shall limit either party's liability for breach of its confidentiality obligations hereunder." Replace the cap entirely; do not accept a carve-out that leaves a cap for other breaches without attorney review.

§7 Residuals | Permits use of information retained in unaided memory; playbook prohibits any residuals clause. In a mutual NDA this cuts against our client as discloser, and the pilot context makes residual use of technical information likely. | High | Delete §7 in its entirety. If counterparty insists, escalate; playbook position is no residuals clause, so no fallback language is proposed here. [Attorney decision: any fallback.]

§9 Governing law | Delaware; acceptable per playbook. No forum/venue clause is included. | Low | No change to governing law. Consider adding: "The parties consent to the exclusive jurisdiction of the state and federal courts located in Delaware." [Attorney decision: playbook is silent on venue; confirm whether exclusive Delaware venue is desired.]

Missing from the draft (required by playbook)

1. Injunctive relief. Add: "Each party acknowledges that unauthorized use or disclosure of Confidential Information may cause irreparable harm for which monetary damages would be an inadequate remedy, and that the Disclosing Party shall be entitled to seek injunctive or other equitable relief, without the requirement of posting a bond, in addition to any other remedies available at law or in equity."

2. Return/destruction on request. Add: "Upon the Disclosing Party's written request, or upon expiration or termination of this Agreement, the Receiving Party shall promptly return or destroy all Confidential Information of the Disclosing Party, including all copies and derivatives, and shall certify such return or destruction in writing upon request." [Attorney decision: playbook does not address retention exceptions (e.g., routine backups, legal/regulatory retention). Any such exception should be bounded by continuing confidentiality obligations and requires attorney sign-off.]

Other items for attorney attention (not in playbook; flagged, no position assumed)

- Draft provides only clauses 2, 4, 6, 7, 9. Clauses 1, 3, 5, 8 and anything after 9 were not provided; review is limited to what was supplied.
- No stated standard exclusions (public domain, independently developed, rightfully received from third party, prior possession). Confirm whether the full draft contains them.
- No compelled-disclosure carve-out (notice and cooperation). Confirm presence or add.
- No restriction on use to the stated purpose (joint pilot evaluation) or limit on disclosure to need-to-know personnel. Confirm presence or add.
- Mutual structure: all proposed language above is drafted neutrally so it binds both parties, consistent with the client being both discloser and recipient.

