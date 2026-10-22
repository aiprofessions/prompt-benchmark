# Transcript — law-en-nda-redline-01 — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:27:41+00:00
- duration_s: 27.0
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

NDA review — Example Robotics Inc. (mutual NDA, joint pilot evaluation)
Reviewed against client playbook. Draft, for supervising attorney review.

CLAUSE REVIEW

Clause | Issue | Risk | Proposed replacement language
-------|-------|------|------------------------------
§2 Definition | Marking-only definition. Oral/visual disclosures (demos, pilot discussions) are excluded entirely; unmarked written material is also unprotected. Playbook requires oral/visual coverage with 30-day written summary. | High | "Confidential Information" means (a) information disclosed in tangible form that is marked "Confidential" or similar, and (b) information disclosed orally or visually that is identified as confidential at the time of disclosure and summarized in writing, designated as confidential, and delivered to the Receiving Party within thirty (30) days after disclosure. [Attorney decision: whether to also push for "reasonably should be understood to be confidential" catch-all; playbook is silent.]

§4 Term | 1 year from disclosure; no trade-secret carve-out. Playbook: 3 years; trade secrets protected while they remain trade secrets. Note the draft runs from each disclosure, not from expiration/termination — confirm which trigger the client wants. | High | Each party's obligations under this Agreement shall continue for three (3) years from the date of disclosure of the relevant Confidential Information; provided that, with respect to any Confidential Information that constitutes a trade secret under applicable law, such obligations shall continue for so long as such information remains a trade secret. [Attorney decision: trigger date — from disclosure vs. from expiration of the Agreement.]

§6 Remedies | $5,000 aggregate cap effectively eliminates any remedy for breach. Playbook: no liability cap for breach of confidentiality. Also no injunctive relief language. | High | Delete the cap. Replace with: Each party acknowledges that unauthorized use or disclosure of Confidential Information may cause irreparable harm for which monetary damages would be an inadequate remedy. The Disclosing Party shall be entitled to seek injunctive or other equitable relief, without the requirement to post bond, in addition to any other remedies available at law or in equity. [Attorney decision: if counterparty insists on some cap, whether a cap on non-confidentiality claims only is acceptable; playbook addresses confidentiality breach only.]

§7 Residuals | Unaided-memory residuals clause. Playbook: no residuals clause. In a robotics pilot this is a significant leakage path for technical know-how, and it undercuts the trade-secret survival in §4. | High | Delete §7 in its entirety. [If counterparty refuses, escalate to supervising attorney — playbook gives no fallback. Any fallback would at minimum need to exclude trade secrets and intentional memorization, and grant no license to IP.]

§9 Governing law | Delaware. Acceptable per playbook. Draft does not specify venue/jurisdiction or whether Delaware's conflict-of-laws rules are excluded. | Low | No change to Delaware. Suggest adding: "...without regard to its conflict-of-laws principles. The parties consent to the exclusive jurisdiction of the state and federal courts located in Delaware." [Attorney decision: venue is not in the playbook; confirm client preference.]

MISSING FROM THE NDA (REQUIRED BY PLAYBOOK)

1. Return/destruction of Confidential Information on request. Not present. Proposed: Upon the Disclosing Party's written request, or upon expiration or termination of this Agreement, the Receiving Party shall promptly return or destroy all Confidential Information (including copies, notes, and derivatives) and, upon request, certify such return or destruction in writing. [Attorney decision: whether to allow a standard carve-out for one archival copy held by legal/compliance and for automated backup systems, subject to continuing confidentiality.]

2. Injunctive relief. Not present. Addressed in §6 replacement above.

3. Oral/visual disclosure coverage. Not present. Addressed in §2 replacement above.

4. Trade-secret survival. Not present. Addressed in §4 replacement above.

OTHER OBSERVATIONS (not in playbook — flag only)

- Mutuality: the playbook and client description say mutual, but §7 refers to "Receiving Party" in the singular and §6 says "each party." Confirm the full draft is drafted reciprocally throughout.
- Standard exclusions (public domain, independently developed, rightfully received from third party, already known) and a compelled-disclosure provision do not appear in the excerpted clauses. Confirm they exist elsewhere in the draft; if not, they should be added.
- Purpose limitation: confirm the draft restricts use to evaluating the joint pilot.
- Only the excerpted clauses (§§2, 4, 6, 7, 9) were reviewed; the remaining sections of the counterparty draft were not provided.

