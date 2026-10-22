# Transcript — skill lawyers-nda-review [en] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:59:28+00:00
- duration_s: 49.7
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

SUMMARY

  Confidentiality: de-identify party names and deal details before sharing, and use only tools your firm has approved for this data. "Sample Biotech LLC" is marked fictional, so I have reproduced it as given.
  Client role: Disclosing party (one-way NDA) | Jurisdiction: New York, as stated in §10
  Scope: Excerpts. Only §§1, 3, 5, 8 and 10 were supplied. Playbook version: not provided.
  Clauses reviewed: 5 | Present-clause issues: 3 | Missing provisions: 2 | Fully compliant clauses: 1
  Priority items:
    - Two mandatory provisions were not found in the excerpt: compelled-disclosure notice-and-cooperation and no-license. Both are provisionally High.
    - §8 non-solicitation conflicts with the playbook's "no non-solicitation" position.
    - §3 lacks the need-to-know and written-obligation limits on onward disclosure.
    - §5 term is 2 years. The playbook requires 5 years plus trade-secret protection.

ISSUE TABLE

  §3 Permitted disclosure
    Draft: "Recipient may disclose Confidential Information to its affiliates, contractors and advisors."
    Playbook: Disclosure only to Representatives who have a need to know and who are bound by written confidentiality obligations at least as protective. No fallback supplied.
    Gap: The clause has no need-to-know limit and no requirement of written obligations at least as protective. It also does not use a "Representatives" concept.
    Risk: Medium, provisional. This is a substantive departure, but no walk-away point is stated.
    Proposed language: Replace §3 with:
      "Recipient may disclose Confidential Information only to its Representatives who have a need to know such Confidential Information and who are bound by written confidentiality obligations at least as protective as those in this Agreement."
    Note: "Representatives" needs a definition. See Question 1.

  §5 Term
    Draft: "Term: obligations last 2 years from the Effective Date."
    Playbook: 5-year term. Trade secrets stay protected for as long as they remain trade secrets. No fallback supplied.
    Gap: The term is 3 years short, and the clause has no trade-secret carve-out.
    Risk: Medium, provisional. This is a substantive departure, but no walk-away point is stated.
    Proposed language: Replace §5 with:
      "Term: obligations last 5 years from the Effective Date; provided that, with respect to Confidential Information that constitutes a trade secret, such obligations continue for as long as such information remains a trade secret."
    See Question 2.

  §8 Non-solicitation
    Draft: "Neither party will solicit the other's employees for 24 months."
    Playbook: No non-solicitation clauses in NDAs.
    Gap: The draft includes a non-solicitation clause. Because it is mutual ("Neither party"), it also binds the client.
    Risk: Medium, provisional. The playbook is categorical but does not label this a walk-away point. See Question 3.
    Proposed language: Replace §8 with "[Intentionally omitted.]"

MISSING PROVISIONS

  Compelled disclosure: notice and cooperation
    Playbook: Must include notice-and-cooperation for compelled disclosure.
    Coverage: Not found in supplied excerpt; full NDA check required. §§2, 4, 6, 7 and 9 were not supplied.
    Risk: High, provisional. The playbook expressly makes this mandatory.
    Proposed language: Insert at a location pending review of the full NDA:
      "If Recipient is legally compelled to disclose any Confidential Information, Recipient shall [LANGUAGE PENDING ATTORNEY INSTRUCTION: timing of notice] notify Discloser and cooperate with Discloser [LANGUAGE PENDING ATTORNEY INSTRUCTION: scope of cooperation]."
    See Question 4.

  No license
    Playbook: Must include a no-license clause.
    Coverage: Not found in supplied excerpt; full NDA check required.
    Risk: High, provisional. The playbook expressly makes this mandatory.
    Proposed language: Insert at a location pending review of the full NDA:
      "Nothing in this Agreement grants Recipient any license or other right in or to any Confidential Information."
    See Question 5.

CLAUSES THAT COMPLY

  §1: Covers information "in any form, whether or not marked," which matches the playbook definition position. No change recommended.

QUESTIONS FOR THE SUPERVISING ATTORNEY

  1. §3: How should "Representatives" be defined? One option is to keep the draft's categories (affiliates, contractors and advisors), but that is a substantive choice the playbook does not make. Should "need to know" be tied to the Purpose (evaluating the licensing deal)? The playbook does not say.
  2. §5: Should the 5-year term run from the Effective Date, as the draft does now, or from each disclosure? Should "trade secret" be defined, or tied to a governing statute? If so, [AUTHORITY TO BE LOCATED].
  3. §8: The playbook says "no non-solicitation clauses." Should this be treated as a walk-away point, which would raise the rating to High? Is any fallback authorized?
  4. Compelled disclosure: Please specify the notice timing and the scope of cooperation. Examples of what needs deciding include whether the clause should cover protective-order assistance or limit disclosure to the portion legally required. I have not drafted either because the playbook does not specify them.
  5. No-license: Should the clause also address implied rights (by implication, estoppel or otherwise)? The playbook does not specify, so I have not added it.
  6. §10 Forum: The New York governing-law sentence meets the playbook's "New York or Delaware" position. However, "exclusive jurisdiction of the courts of New York County" has no playbook position, so I have not assessed it. I have not listed §10 as fully compliant for that reason. What position should apply?
  7. Ratings: All ratings are provisional defaults. Do you confirm High for the two mandatory missing provisions and Medium for §§3, 5 and 8?

LIMITS

  - Review is against the supplied playbook only. No outside substantive requirements were applied.
  - Inputs not provided:
    - Playbook version
    - Risk criteria
    - Authorized fallbacks
    - Definitions of "Recipient," "Discloser," "Effective Date" and "Purpose"
  - Scope: Excerpts only. §§2, 4, 6, 7, 9 and any later sections were not reviewed. The missing-provision findings must be checked against the full NDA, and insertion locations depend on it.
  - Risk method: Provisional defaults (High = mandatory provision absent or walk-away crossed; Medium = other substantive departure). Counsel must confirm.
  - Authority needed: [AUTHORITY TO BE LOCATED] for any trade-secret definition (Question 2).
  - Professional duties (US/New York): ABA Formal Opinion 512, Generative Artificial Intelligence Tools (July 29, 2024), https://www.americanbar.org/content/dam/aba/administrative/professional_responsibility/ethics-opinions/aba-formal-opinion-512.pdf. The supervising attorney should also check applicable New York rules.
  - Licensed supervising counsel must verify the source text, proposed language, ratings, cross-references and enforceability before use.
  - This is a draft for attorney review. It is not legal advice and is not ready for external use.

