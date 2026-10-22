# Transcript — law-en-nda-redline-01 — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:11:00+00:00
- duration_s: 29.9
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

NDA REVIEW: Example Robotics Inc. (mutual NDA, joint pilot evaluation)
Counterparty draft vs. client playbook

Because the agreement is mutual, each position below binds Example Robotics as a receiving party as well as protecting it as a discloser.

------------------------------------------------------------
CLAUSE | ISSUE | RISK | PROPOSED REPLACEMENT LANGUAGE
------------------------------------------------------------

§2 Confidential Information
  Issue: Covers only information marked "Confidential" when disclosed. Oral and visual disclosures, which are common in pilot discussions and demos, fall outside the definition.
  Risk: HIGH
  Proposed: "Confidential Information" means non-public information disclosed by a party (i) in written or other tangible form and marked "Confidential" at the time of disclosure, or (ii) orally or visually, provided the disclosing party summarizes it in writing, marked "Confidential," and delivers the summary to the receiving party within thirty (30) days after disclosure.
  Attorney decision: Should information disclosed orally or visually be protected during the 30-day window before the summary is delivered? The playbook does not say.

§4 Term
  Issue: Obligations survive only 1 year after disclosure. The playbook requires 3 years, plus protection of trade secrets for as long as they remain trade secrets.
  Risk: HIGH
  Proposed: The receiving party's obligations under this Agreement shall continue for three (3) years after [the date of disclosure / the expiration or termination of this Agreement]. With respect to any Confidential Information that constitutes a trade secret under applicable law, such obligations shall continue for so long as such information remains a trade secret.
  Attorney decision: The playbook says "3 years" but does not say when the period starts. Choose between the bracketed options.

§6 Remedies (liability cap)
  Issue: A $5,000 aggregate cap applies to all liability, including breach of confidentiality, which the playbook prohibits. The clause also lacks the injunctive relief the playbook requires.
  Risk: HIGH
  Proposed: Nothing in this Agreement limits either party's liability for breach of its confidentiality or non-use obligations. Each party acknowledges that unauthorized use or disclosure of the other party's Confidential Information may cause irreparable harm for which monetary damages would be inadequate, and that the disclosing party shall be entitled to seek injunctive or other equitable relief, without the necessity of posting a bond, in addition to any other remedies available at law or in equity.
  Attorney decision:
    (a) Should any cap remain for liability other than confidentiality breaches, or should §6 be deleted and replaced entirely?
    (b) Removing the cap is mutual, so Example Robotics's own exposure as a receiving party becomes uncapped. Confirm the client accepts this.
    (c) The bond waiver is not in the playbook. Include it or strike it.

§7 Residuals
  Issue: The residuals clause lets the receiving party use any retained information, which undermines the NDA's protections. The playbook says no residuals clause.
  Risk: HIGH
  Proposed: Delete §7 in its entirety. Optionally add: "No license or right to use Confidential Information is granted except as expressly set forth in this Agreement, including for the Purpose."

§9 Governing Law
  Issue: Delaware matches the playbook. The clause does not specify venue or jurisdiction.
  Risk: LOW
  Proposed: Accept as drafted.
  Attorney decision: The playbook is silent on forum. Decide whether to propose a venue clause (e.g., state or federal courts located in Delaware), and confirm that any venue clause preserves the right to seek injunctive relief in any court of competent jurisdiction.

------------------------------------------------------------
MISSING PLAYBOOK REQUIREMENTS
------------------------------------------------------------

1. Injunctive relief
   The draft does not provide for it. Language is included in the §6 replacement above, or it can go in a standalone clause.

2. Return or destruction on request
   The draft contains no such provision. Proposed:
   "Upon the disclosing party's written request, the receiving party shall promptly return or destroy all Confidential Information of the disclosing party in its possession or control, including all copies, and, upon request, certify such return or destruction in writing."
   Attorney decision:
     (a) Should there be a carve-out for copies retained in automatic electronic backups or required by law, with those copies remaining subject to confidentiality? The playbook is silent.
     (b) The certification requirement is not in the playbook. Include it or strike it.

3. Oral and visual disclosures
   These are not covered anywhere in the draft. They are addressed in the §2 replacement above.

4. Trade secret protection beyond the term
   The draft does not provide it. This is addressed in the §4 replacement above.

------------------------------------------------------------
NOTE
------------------------------------------------------------

This review covers only the five clauses provided. The remaining provisions (§§1, 3, 5, 8, and any after §9) were not reviewed. They may affect the analysis, for example through the definition of Purpose, standard exclusions, or permitted disclosures.

