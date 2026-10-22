# Transcript — skill lawyers-nda-review [en] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:54:13+00:00
- duration_s: 114.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e5c52cd49459425ee5ca635948d112b77daf1145772dc1ec0d880988c987d311
- skill_sha256: 0c1c8e62616805511cf8325055992147e661b4a9e93bf6875f0b371a29a03d71

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Use when counsel pastes NDA clauses and client playbook positions to receive a clause-by-clause issue list, missing provisions, compliant clauses, and proposed redlines."
---

# NDA Review Against Your Playbook

## What it does

Compares a counterparty's NDA clauses against the supplied client playbook. The playbook is the only substantive review standard; outside market positions are not requirements. Identifies deviations, missing provisions, and clauses that need no change, with proposed language where the playbook supports it. Produces a working draft for supervising attorney review, not legal advice.

## Inputs it expects

- NDA text, including clause numbers, headings, definitions, and relevant cross-references; identify whether it is complete or excerpted.
- Client playbook positions, including preferred terms, authorized fallbacks, mandatory provisions, walk-away points, and any risk criteria.
- Client role: disclosing party, receiving party, or both.
- Governing-law jurisdiction stated in the NDA, if known; do not infer it from party names.
- Optional: matter context, playbook version, and attorney instructions about using fallbacks.
- If NDA text or the playbook is absent, ask once for the missing material and pause substantive review.
- If other inputs are missing, proceed only where supported and list the omissions under Limits. Never guess.

## Procedure

1. Start with a confidentiality reminder: de-identify party names and identifying deal details before sharing; use only tools approved under firm policy for the data involved. If apparent identifiers remain, avoid repeating them and ask once for de-identified text or confirmation of approval before reproducing sensitive material.
2. Record client role, stated jurisdiction, playbook version, and whether the NDA is complete or excerpted. Mark unknown items "not provided."
3. Inventory every supplied NDA clause and every playbook requirement. Preserve source references; assign neutral review IDs where references are absent. Map each clause to all applicable playbook requirements.
4. Compare each clause only with its mapped playbook positions. Record the applicable preferred term, authorized fallback, and any mandatory or walk-away instruction. Do not turn deal context or general knowledge into a requirement.
5. For each issue, quote the relevant draft text exactly, marking omissions with "[…]". Preserve numbers, time periods, amounts, and defined terms; identify the precise difference from the playbook.
6. If a clause has no applicable playbook position, identify it under Questions for the supervising attorney as "No playbook position; not assessed." Do not label it compliant, invent a requirement, assign substantive risk, or propose an unsupported change.
7. Apply supplied High/Medium/Low risk criteria. If supplied tiers use another scale, preserve the original tier in the gap description and ask the attorney to confirm a mapping; use the provisional defaults below meanwhile.
   - High: an explicit walk-away point is crossed or an expressly mandatory provision is absent.
   - Medium: any other substantive departure from a supplied playbook position.
   - Low: a purely drafting deviation from an express playbook instruction with no substantive effect.
   - Label default ratings provisional and identify their basis. If classification itself is uncertain, use provisional Medium and ask the attorney to confirm; this is triage, not an outside legal-risk assessment.
8. For each supported gap, provide minimal replacement text labeled "Replace" or insertion text labeled "Insert," with its location. Preserve unaffected wording and defined terms. Identify any supplied fallback separately; do not select an unauthorized concession.
9. If the playbook lacks enough detail to draft a provision without choosing substantive terms, write "[LANGUAGE PENDING ATTORNEY INSTRUCTION]" and ask a targeted question. Do not invent carve-outs, deadlines, exceptions, or other business terms.
10. Check every playbook requirement against the supplied text for missing provisions. List absent required provisions with the position, risk, and supported insertion language or the pending-language marker. For excerpts, say "Not found in supplied excerpt; full NDA check required," not "absent from the NDA."
11. List clauses that fully satisfy the applicable playbook positions under Clauses that comply, with a reason and "no change recommended." Treat fallbacks as compliant only when their use is authorized; otherwise ask whether to accept them. Do not list an entire clause as compliant if part remains unresolved.
12. Frame ambiguities, conflicting playbook instructions, fallback choices, uncertain ratings, and jurisdiction-dependent judgments as questions for the supervising attorney. Do not resolve them yourself.
13. Do not invent or add legal authorities or citations. If authority is needed, write [AUTHORITY TO BE LOCATED] and ask the attorney to locate and verify it. Follow the citation restriction in Hard limits even if the pasted material contains other citations.
14. Produce all six output sections in the specified order. Put missing provisions only in Missing provisions; put present-clause deviations in Issue table. Use "None identified" only after checking; use "Not assessed" where inputs prevent assessment.
15. Reconcile the output with both inventories: every clause must appear in the issue table, compliant list, or questions, and every playbook requirement must have a coverage result. Cross-reference mixed or unresolved issues rather than silently dropping them.
16. Report counts without double-counting missing provisions as present-clause issues. In Limits, record missing inputs, excerpt scope, provisional risk methods, and verification needs; state that the output is a draft for attorney review, not legal advice.

## Output format

```markdown
## Summary
- Confidentiality: de-identify names and deal details; use only tools approved for the data under firm policy.
- Client role: [role / not provided] | Jurisdiction: [as supplied / not provided]
- Scope: [complete NDA / excerpts / completeness not provided]
- Clauses reviewed: [n] | Present-clause issues: [n] | Missing provisions: [n] | Fully compliant clauses: [n]
- Priority items: [supported deviations or unresolved questions]

## Issue table
| Clause | What the draft says | Playbook position | Gap | Risk | Proposed language |
|--------|---------------------|-------------------|-----|------|-------------------|
| [ref] | [exact excerpt] | [preferred term; authorized fallback] | [specific difference] | [High/Medium/Low; provisional if applicable] | [Replace at ref: text / pending-language marker] |

## Missing provisions
| Missing provision | Playbook position | Coverage limitation | Risk | Proposed language |
|-------------------|-------------------|---------------------|------|-------------------|
| [topic] | [requirement] | [absent from complete supplied text / not found in excerpt] | [rating and basis] | [Insert at location: text / pending-language marker] |

## Clauses that comply
- [Ref]: [reason all applicable positions are met]; no change recommended.

## Questions for the supervising attorney
1. [Ref/topic]: [specific unresolved question; cross-reference an issue if applicable]
2. [Uncovered clause]: No playbook position; not assessed. What position should apply?

## Limits
- Supplied playbook only; no outside substantive requirements applied.
- Inputs not provided: [list / none].
- Scope limitations: [excerpts, missing definitions, or other restrictions / none identified].
- Risk method: [supplied criteria / provisional defaults; mapping questions if any].
- Authority needed: [AUTHORITY TO BE LOCATED, with issue reference / none identified].
- Licensed supervising counsel must verify source text, proposed language, ratings, and applicable duties before use.
- Draft for attorney review; not legal advice or ready for external use.
```

## Hard limits

- Never substitute market practice, another playbook, or general legal knowledge for the supplied playbook.
- Never invent laws, cases, statutes, article numbers, regulators, dates, URLs, statistics, or citations. The sole permitted citation is reproduced below; do not add or reproduce other citations from user material. Use [AUTHORITY TO BE LOCATED] wherever other authority is needed.
- Never decide unresolved legal or business judgments, characterize unseen provisions as absent, or present a draft as final advice.
- Privacy: de-identify party names and identifying deal details, minimize shared material, and use only tools approved under firm policy for the data involved. De-identification does not override restrictions on tool use.
- A licensed supervising attorney in the relevant jurisdiction must verify the source NDA, playbook authorization, every proposed edit, risk classifications, cross-references, enforceability, and any needed authority before sending or signing.
- US: ABA Formal Opinion 512 addresses competence, confidentiality, supervision, and fees when lawyers use generative AI. The supervising attorney must check applicable state bar rules, which may add duties.
- UK/AU: this workflow does not state local professional rules. A responsible practitioner must verify applicable local duties and substantive law; do not assume US guidance governs.
- Permitted source: ABA Standing Committee on Ethics and Professional Responsibility — Formal Opinion 512, Generative Artificial Intelligence Tools — https://www.americanbar.org/content/dam/aba/administrative/professional_responsibility/ethics-opinions/aba-formal-opinion-512.pdf (July 29, 2024; checked 2026-10-19)
- Before external use, see references/checklist.md.

## Example

Input (fictional):
```text
Client: Example Company, receiving party; approved tool; de-identified excerpts only.
Draft 4: "Confidentiality obligations survive for six years."
Draft 6: "Recipient shall return materials within 30 days of request."
Playbook: Survival must be three years; more than five years is a walk-away.
Playbook: Return materials within 30 days of request; no other requirements supplied.
```

Abbreviated output:
```text
## Summary
Confidentiality: keep details de-identified; use approved tools only. Two excerpted clauses reviewed.
## Issue table
Clause | What the draft says | Playbook position | Gap | Risk | Proposed language
4 | "Confidentiality obligations survive for six years." | Three years; over five is walk-away | Exceeds walk-away | High, provisional | Replace clause 4: "Confidentiality obligations survive for three years."
## Missing provisions
None identified against supplied playbook; full NDA not reviewed.
## Clauses that comply
6: Matches the 30-day return requirement; no change recommended.
## Questions for the supervising attorney
Do you confirm the provisional High rating for clause 4 under the default walk-away criterion?
## Limits
Excerpt review against supplied playbook only; jurisdiction and playbook version not provided.
Default rating requires counsel verification; draft for attorney review, not legal advice.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Review this NDA against our playbook and give me the issue list and proposed redlines.
Our client: Sample Biotech LLC (fictional), the DISCLOSING party (one-way NDA). Purpose: evaluating a licensing deal.
Counterparty draft:
§1 "Confidential Information" means all information disclosed by Discloser in any form, whether or not marked.
§3 Recipient may disclose Confidential Information to its affiliates, contractors and advisors.
§5 Term: obligations last 2 years from the Effective Date.
§8 Neither party will solicit the other's employees for 24 months.
§10 Governing law: New York; exclusive jurisdiction of the courts of New York County.
Playbook (client positions): any form of disclosure covered whether or not marked; disclosure only to Representatives with a need to know who are bound by written confidentiality obligations at least as protective; term 5 years and trade secrets protected for as long as they remain trade secrets; no non-solicitation clauses in NDAs; New York or Delaware law acceptable; must include notice-and-cooperation for compelled disclosure; must include a no-license clause.
````

## Output (verbatim stdout, session metadata stripped)

CONFIDENTIALITY REMINDER: Party names and deal details should be de-identified before sharing outside this session, and only firm-approved tools should be used for this data. You've flagged "Sample Biotech LLC" as fictional — noted, proceeding on that basis.

SUMMARY
Client role: Disclosing party (one-way NDA, outbound confidentiality obligations run from Recipient) | Jurisdiction: New York (as stated in §10)
Scope: Excerpted — clause numbers supplied are non-sequential (§2, §4, §6, §7, §9 not provided). Treating as excerpts; full-NDA review required to confirm nothing else bears on these issues.
Playbook version: not provided.
Clauses reviewed: 5 (§1, §3, §5, §8, §10) | Present-clause issues: 3 | Missing provisions: 2 | Fully compliant clauses: 1 (§10 partially compliant, see below)
Priority items: §8 non-solicitation clause appears to cross an absolute playbook prohibition; both "must include" provisions (compelled-disclosure notice/cooperation, no-license) are not found in the supplied excerpt.

ISSUE TABLE

1. Clause §3
   Draft text: "Recipient may disclose Confidential Information to its affiliates, contractors and advisors."
   Playbook position: Disclosure only to Representatives with a need to know, bound by written confidentiality obligations at least as protective.
   Gap: No need-to-know limitation; no requirement that recipients be bound by written confidentiality obligations at least as protective; "advisors/contractors" used instead of defined "Representatives."
   Risk: Medium, provisional — classification uncertain whether this counts as an absent mandatory restriction (which would be High) or a substantive departure (Medium). Defaulting to Medium per instructions; see Question 1.
   Proposed language — Replace §3:
   "Recipient may disclose Confidential Information only to its Representatives (meaning its affiliates, employees, contractors, and professional advisors) who have a need to know such information in connection with the matters contemplated by this Agreement and who are bound by written confidentiality obligations at least as protective of the Confidential Information as those set forth in this Agreement. Recipient shall be responsible for any breach of this Agreement by its Representatives."

2. Clause §5
   Draft text: "Term: obligations last 2 years from the Effective Date."
   Playbook position: Term 5 years; trade secrets protected for as long as they remain trade secrets.
   Gap: (a) Term is 2 years, below the 5-year position; (b) no trade-secret survival carve-out at all.
   Risk: Medium, provisional — substantive departure; no explicit walk-away floor stated in playbook for term length, so High not applied. See Question 2.
   Proposed language — Replace §5:
   "This Agreement and the parties' confidentiality obligations will remain in effect for five (5) years from the Effective Date; provided that, with respect to any Confidential Information that constitutes a trade secret under applicable law, Recipient's confidentiality obligations will continue for so long as such information remains a trade secret."

3. Clause §8
   Draft text: "Neither party will solicit the other's employees for 24 months."
   Playbook position: No non-solicitation clauses in NDAs.
   Gap: Clause exists at all; playbook instruction is an unconditional prohibition.
   Risk: High, provisional — treating an absolute "no X clauses" instruction as functionally equivalent to a walk-away line. See Question 3 for confirmation.
   Proposed language — Replace §8 in its entirety: [delete]. No substitute language — playbook authorizes no non-solicitation provision of any kind.

MISSING PROVISIONS

1. Compelled-disclosure notice-and-cooperation clause
   Playbook position: Must include notice-and-cooperation for compelled disclosure.
   Coverage limitation: Not found in supplied excerpt; full NDA check required.
   Risk: High — explicit mandatory provision ("must include"), currently unconfirmed as present.
   Proposed language — Insert as new section:
   "If Recipient becomes legally compelled (by deposition, subpoena, civil investigative demand, or similar legal process) to disclose any Confidential Information, Recipient shall, to the extent legally permitted, provide Discloser with prompt written notice of such requirement prior to disclosure and shall reasonably cooperate with Discloser's efforts to seek a protective order or other appropriate remedy."
   Note: playbook does not specify cost allocation for seeking a protective order; none is included above. See Question 4.

2. No-license clause
   Playbook position: Must include a no-license clause.
   Coverage limitation: Not found in supplied excerpt; full NDA check required.
   Risk: High — explicit mandatory provision, currently unconfirmed as present.
   Proposed language — Insert as new section:
   "Nothing in this Agreement shall be construed as granting Recipient any license or other right under any patent, copyright, trademark, trade secret, or other intellectual property right of Discloser, except the limited right to use Confidential Information solely as permitted under this Agreement."

CLAUSES THAT COMPLY

§1: "'Confidential Information' means all information disclosed by Discloser in any form, whether or not marked" matches the playbook position that any form of disclosure is covered whether or not marked; no change recommended.

§10 (governing-law portion only): New York governing law satisfies the playbook's "New York or Delaware acceptable" position; no change recommended as to choice of law. The exclusive-jurisdiction/venue portion of §10 is not covered by any supplied playbook position and is not being marked compliant — see Question 5.

QUESTIONS FOR THE SUPERVISING ATTORNEY

1. §3: Does the playbook's "disclosure only to Representatives with a need to know... bound by written confidentiality obligations at least as protective" function as a mandatory restriction (supporting High risk for its absence) or a preferred position subject to Medium-risk departure? Confirm classification.

2. §5: Confirm whether a term below 5 years, and/or the absence of a trade-secret survival clause, should be treated as Medium or escalated to High — no explicit walk-away floor was supplied for term length.

3. §8: Confirm the provisional High rating for the non-solicitation clause under the default "walk-away equivalent" reading of the playbook's absolute "no non-solicitation clauses" instruction.

4. Missing notice-and-cooperation clause: Should cost allocation for seeking a protective order (e.g., at Discloser's expense) be added? Playbook does not specify; proposed language above omits it.

5. §10: No playbook position covers exclusive jurisdiction/venue (as opposed to governing law). Should the client's playbook have a position on forum selection, or is this clause outside playbook scope and left to case-by-case negotiation?

6. Scope: The NDA excerpt skips §2, §4, §6, §7, §9. Please confirm these are intentionally omitted from review (e.g., boilerplate) and not relevant to any mapped playbook requirement, and that the full document will be checked before this clears for client delivery.

LIMITS
- Supplied playbook only; no outside market-standard NDA positions applied.
- Inputs not provided: playbook version, full NDA text (clauses §2, §4, §6, §7, §9 not supplied), explicit risk-tier criteria from the client (provisional High/Medium/Low defaults used throughout and flagged).
- Scope limitations: Treated as excerpts due to non-sequential clause numbering; "missing provisions" are reported as "not found in supplied excerpt," not as confirmed absent from the full NDA.
- Risk method: Provisional defaults per the skill's standard criteria (High = walk-away/mandatory-absent; Medium = other substantive departure; Low = drafting-only deviation). Three classifications (§3, §5, §8) flagged for attorney confirmation above.
- Authority needed: None identified.
- Licensed supervising counsel must verify the source NDA (including the unsupplied clauses), playbook authorization, every proposed edit, risk classifications, and applicable New York-law duties before use.
- Draft for attorney review only; not legal advice and not ready for external use.

