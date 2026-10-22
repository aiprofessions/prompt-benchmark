# Transcript — law-en-nda-redline-01 — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:10:20+00:00
- duration_s: 26.5
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

NDA REVIEW — Example Robotics Inc. (mutual NDA, joint pilot evaluation)

Clause | Issue | Risk | Proposed replacement language
-------|-------|------|------------------------------
§2 Definition | Covers only information marked "Confidential" at disclosure. Oral/visual disclosures and unmarked documents fall outside protection, contrary to playbook. | High | "Confidential Information" means all non-public information disclosed by either party, whether in writing, orally, visually, or by inspection, that is marked or identified as confidential at the time of disclosure or, if disclosed orally or visually, is summarized in writing and designated confidential within thirty (30) days of disclosure.
§4 Term | Obligations expire 1 year after disclosure; playbook requires 3 years, and trade secrets protected indefinitely. Also "after disclosure" (vs. after termination/expiry) is a rolling clock that shortens protection. | High | Each party's obligations under this Agreement shall continue for three (3) years from the date of disclosure; provided that, with respect to any Confidential Information that constitutes a trade secret under applicable law, such obligations shall continue for so long as such information remains a trade secret.
§6 Remedies (cap) | $5,000 aggregate liability cap applies to breach of confidentiality; playbook requires no cap. Cap effectively makes the NDA unenforceable in practice. | High | Nothing in this Agreement limits either party's liability for breach of its confidentiality obligations. [Alternative if counterparty insists on some cap: exclude breach of §[confidentiality], misuse of Confidential Information, and trade secret misappropriation from any limitation — flag for supervising attorney.]
§6 Remedies (injunctive relief) | No express acknowledgment of irreparable harm / right to equitable relief; playbook requires it. | High | Each party acknowledges that unauthorized use or disclosure of Confidential Information may cause irreparable harm for which monetary damages would be inadequate, and the Disclosing Party shall be entitled to seek injunctive or other equitable relief, without the requirement to post a bond, in addition to any other remedies available at law or in equity.
§7 Residuals | Unaided-memory residuals clause; playbook position is no residuals clause. Particularly risky for a robotics pilot where technical know-how can be carried in memory. | High | Delete §7 in its entirety. [If counterparty will not delete, do not agree to a narrowed version without supervising attorney sign-off.]
§9 Governing law | Delaware; consistent with playbook. No forum/venue clause specified — note only. | Low | No change. [Consider adding exclusive venue/jurisdiction if the supervising attorney wants it; playbook is silent.]

MISSING FROM NDA (required by playbook)

1. Return/destruction of Confidential Information on request. Proposed: "Upon the Disclosing Party's written request, or upon termination or expiration of this Agreement, the Receiving Party shall promptly return or destroy all Confidential Information and copies thereof and, on request, certify such return or destruction in writing. The Receiving Party may retain one archival copy solely to comply with legal or regulatory obligations, which remains subject to this Agreement." (Archival carve-out is a common ask — confirm acceptable to supervising attorney; playbook does not address it.)

2. Injunctive relief (see §6 row above) — absent from the draft, not merely deficient.

3. Written-summary mechanism for oral/visual disclosures (see §2 row) — absent from the draft.

ITEMS FOR SUPERVISING ATTORNEY DECISION

- Whether to accept any liability cap for non-confidentiality breaches (playbook only prohibits cap for breach of confidentiality).
- Fallback position on §7 if counterparty refuses full deletion.
- Whether to add venue/dispute resolution to §9 (playbook silent).
- Whether an archival-copy exception in the return/destruction clause is acceptable.
- Draft does not define "Purpose" or restrict use to the joint pilot evaluation — not a stated playbook item, but confirm whether a purpose-limitation clause should be requested.

Note: Only §§2, 4, 6, 7, 9 were provided; other sections of the counterparty draft were not reviewed.

