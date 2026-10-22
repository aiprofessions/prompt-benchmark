# Transcript — skill lawyers-nda-review [en] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:43:47+00:00
- duration_s: 94.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: e5c52cd49459425ee5ca635948d112b77daf1145772dc1ec0d880988c987d311
- skill_sha256: e44ff2e1596842c06a940bb6f03e6272f621c592a3014738e44a9beb4e74e036

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
- If other inputs are missing, proceed only where supported and list the omissions under Summary. Never guess.

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
13. Do not invent or add legal authorities or citations. If authority is needed, put [AUTHORITY TO BE LOCATED] under Questions for the supervising attorney with the issue reference and a request that counsel locate and verify it.
14. Do not cite any authority, regulator guidance, ethics opinion, case, or statute in the review output unless it appears in the user's input. The official source in Hard limits is for the attorney's own reading, not for inclusion in the review output. Reproduce any necessary user-supplied citation only as written, labeled "user-supplied; not verified"; do not endorse it or expand it from memory. The Limits section must contain only: "The supervising attorney verifies applicable law and professional rules."
15. Produce all six output sections in the specified order. Put missing provisions only in Missing provisions; put present-clause deviations in Issue table. Use "None identified" only after checking; use "Not assessed" where inputs prevent assessment.
16. Reconcile the output with both inventories: every clause must appear in the issue table, compliant list, or questions, and every playbook requirement must have a coverage result. Cross-reference mixed or unresolved issues rather than silently dropping them.
17. Report counts without double-counting missing provisions as present-clause issues. In Summary, record missing inputs, excerpt scope, provisional risk methods, and that the output is a draft for attorney review, not legal advice.
18. Before returning the review, remove any citation not present in the user's input, verify that authority placeholders appear in attorney questions, and confirm that Limits contains only the required verification sentence.

## Output format

```markdown
## Summary
- Draft for attorney review; not legal advice or ready for external use.
- Confidentiality: de-identify names and deal details; use only tools approved for the data under firm policy.
- Standard: supplied playbook only; no outside substantive requirements applied.
- Client role: [role / not provided] | Jurisdiction: [as supplied / not provided]
- Playbook version: [version / not provided] | Other missing inputs: [list / none]
- Scope: [complete NDA / excerpts / completeness not provided]; restrictions: [missing definitions or other limitations / none identified]
- Risk method: [supplied criteria / provisional defaults; mapping questions if any]
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
2. [Uncovered clause, if any]: No playbook position; not assessed. What position should apply?
3. [If authority is needed]: [AUTHORITY TO BE LOCATED] — [issue]. Will counsel locate and verify the necessary authority?

## Limits
The supervising attorney verifies applicable law and professional rules.
```

## Hard limits

- Never substitute market practice, another playbook, or general legal knowledge for the supplied playbook.
- Never invent laws, cases, statutes, article numbers, regulators, dates, URLs, statistics, or citations. Use [AUTHORITY TO BE LOCATED] in attorney questions wherever authority is needed.
- Never cite any authority, regulator guidance, case, or statute in the review output, including the source listed below, unless the user's input contains it. The source below is for the attorney's own reading only. User-supplied authorities are unverified input, not established law.
- Never decide unresolved legal or business judgments, characterize unseen provisions as absent, or present a draft as final advice.
- Privacy: de-identify party names and identifying deal details, minimize shared material, and use only tools approved under firm policy for the data involved. De-identification does not override restrictions on tool use.
- A licensed supervising attorney in the relevant jurisdiction must verify the source NDA, playbook authorization, every proposed edit, risk classifications, cross-references, enforceability, and any needed authority before sending or signing.
- US: the official source below addresses competence, confidentiality, supervision, and fees when lawyers use generative AI. The supervising attorney must check applicable state bar rules, which may add duties.
- UK/AU: this workflow does not state local professional rules. A responsible practitioner must verify applicable local duties and substantive law; do not assume US guidance governs.
- Source for the attorney's reading (not for review output): ABA Standing Committee on Ethics and Professional Responsibility — Formal Opinion 512, Generative Artificial Intelligence Tools — https://www.americanbar.org/content/dam/aba/administrative/professional_responsibility/ethics-opinions/aba-formal-opinion-512.pdf (July 29, 2024; checked 2026-10-19)
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
Draft for attorney review, not legal advice. Keep details de-identified; use approved tools only.
Supplied playbook only; two excerpted clauses reviewed. Jurisdiction and playbook version not provided; default risk rating is provisional.
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
The supervising attorney verifies applicable law and professional rules.
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

## Summary
- Draft for attorney review; not legal advice or ready for external use.
- Confidentiality: de-identify names and deal details before any external sharing; use only tools approved under firm policy for this data. (Party name supplied is stated as fictional.)
- Standard: supplied playbook only; no outside market-practice requirements applied.
- Client role: Disclosing party (one-way NDA) | Jurisdiction: New York, as stated in §10
- Playbook version: not provided | Other missing inputs: full NDA text not supplied (excerpted clauses only); "Representatives" and "Purpose" not defined in supplied excerpt
- Scope: Excerpts only (§1, §3, §5, §8, §10 supplied); restrictions: cannot confirm presence/absence of other clauses (e.g., definitions of "Representatives," "Purpose," remedies, no-license, compelled-disclosure provisions) outside what is shown
- Risk method: Provisional defaults (playbook did not supply its own High/Medium/Low criteria); one classification flagged as uncertain per Hard limits/Step 7 and defaulted to provisional Medium pending attorney confirmation
- Clauses reviewed: 5 | Present-clause issues: 3 | Missing provisions: 3 | Fully compliant clauses: 1 (§1); §10 partially compliant (see table/questions)
- Priority items: §8 non-solicitation clause present despite playbook's flat prohibition (classification uncertain — see Question 1); two "must include" provisions (notice-and-cooperation; no-license) not found in the excerpt and need full-NDA confirmation; §5 term below playbook position with no trade-secret carve-out anywhere in the supplied text.

## Issue table
| Clause | What the draft says | Playbook position | Gap | Risk | Proposed language |
|--------|---------------------|-------------------|-----|------|-------------------|
| §3 | "Recipient may disclose Confidential Information to its affiliates, contractors and advisors." | Disclosure only to Representatives with a need to know who are bound by written confidentiality obligations at least as protective. | No "need to know" limitation; no requirement that recipients be bound by written confidentiality obligations at least as protective; uses undefined categories (affiliates/contractors/advisors) instead of playbook's "Representatives" standard. | Medium | Replace §3: "Recipient may disclose Confidential Information only to its Representatives who have a need to know such information for the Purpose and who are bound by written confidentiality obligations at least as protective of the Confidential Information as those set forth in this Agreement." |
| §5 | "Term: obligations last 2 years from the Effective Date." | Term 5 years. | Term is 2 years versus playbook's 5-year position. | Medium | Replace §5: "Term: obligations last five (5) years from the Effective Date." |
| §8 | "Neither party will solicit the other's employees for 24 months." | No non-solicitation clauses in NDAs. | Draft includes a non-solicitation clause the playbook flatly prohibits. Classification is uncertain: this is an absolute "must not include" instruction that does not map cleanly onto the walk-away/mandatory-absence criteria used for High; defaulted to provisional Medium pending attorney confirmation (see Question 1). | Medium, provisional (classification uncertain — attorney confirmation requested) | Replace §8: [Delete Section 8 in its entirety.] |

## Missing provisions
| Missing provision | Playbook position | Coverage limitation | Risk | Proposed language |
|-------------------|-------------------|---------------------|------|-------------------|
| Trade-secret survival carve-out | Trade secrets protected for as long as they remain trade secrets, in addition to the 5-year general term. | Not found in supplied excerpt; full NDA check required. | Medium (position stated but not expressly flagged "mandatory" in playbook text) | Insert at §5 (Term): ", provided that obligations with respect to any Confidential Information that constitutes a trade secret under applicable law shall survive for as long as such information remains a trade secret." |
| Notice-and-cooperation for compelled disclosure | "Must include notice-and-cooperation for compelled disclosure." | Not found in supplied excerpt; full NDA check required. | High (playbook uses "must include," an express mandatory instruction) | [LANGUAGE PENDING ATTORNEY INSTRUCTION] — playbook does not specify notice timing (e.g., "prompt," a stated number of days) or the scope of required cooperation (e.g., seeking a protective order, cost allocation). Targeted question below. |
| No-license clause | "Must include a no-license clause." | Not found in supplied excerpt; full NDA check required. | High (playbook uses "must include," an express mandatory instruction) | Insert new section: "No license or other right is granted to Recipient under this Agreement, by implication or otherwise, in or to any Confidential Information." |

## Clauses that comply
- §1: "means all information disclosed by Discloser in any form, whether or not marked" matches the playbook's position that any form of disclosure is covered whether or not marked; no change recommended.
- §10 (governing-law portion only): "Governing law: New York" falls within the playbook's acceptable set (NY or Delaware); no change recommended on this portion. The exclusive-jurisdiction/venue portion of §10 (courts of New York County) has no corresponding playbook position and is addressed separately under Questions below — §10 is not listed as fully compliant.

## Questions for the supervising attorney
1. §8 (non-solicitation): The playbook states "no non-solicitation clauses in NDAs" as an absolute prohibition, which does not map cleanly onto the supplied High/Medium/Low default criteria (walk-away crossed / mandatory provision absent). I defaulted to provisional Medium per the triage rule for uncertain classification. Should this be elevated to High given the playbook's flat "no" instruction, or does counsel have authorized flexibility here?
2. §10 (exclusive jurisdiction/venue — courts of New York County): No playbook position; not assessed. What position should apply, if any, beyond the governing-law choice?
3. Notice-and-cooperation clause (missing provision, excerpt-limited): Please confirm this is genuinely absent from the full NDA, and provide the required notice period and scope of cooperation so language can be drafted rather than left as [LANGUAGE PENDING ATTORNEY INSTRUCTION].
4. "Representatives" (used in proposed §3 redline): The supplied excerpt does not show whether "Representatives" is a defined term elsewhere in the NDA, or whether it needs to be defined to encompass (or replace) "affiliates, contractors and advisors." Please confirm the defined-term status and scope before this redline is finalized.
5. Trade-secret carve-out and no-license clause (missing provisions): Please confirm these are genuinely absent from the full NDA text, since only excerpts were supplied.

## Limits
The supervising attorney verifies applicable law and professional rules.

