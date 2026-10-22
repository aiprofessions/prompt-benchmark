# Transcript — skill real-estate-compliant-listing [en] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:54:19+00:00
- duration_s: 35.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 9925732aa90f3483d1fb4354a85ae98bc82422c0cf4e5dc513ecc0c31b48a0bc
- skill_sha256: 9d3d51042c292300ba33a94809580e39d742331b5e702298612121e100607163

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: real-estate-compliant-listing
description: "Use when an agent pastes property facts and rough notes; returns property-focused listing copy, a social caption, and an audit list for compliance review."
---

# Fair-Housing-Safe Listing Copy

## What it does

Turns property facts and seller or agent notes into property-focused listing copy and a social caption. Removes language about preferred buyers or tenants, unsupported claims, and unverified assertions. Returns an audit list and verification questions for professional review; it does not certify legal compliance.

## Inputs it expects

- Property facts intended for publication: location, price, bedrooms, bathrooms, area, fees, features, and included equipment.
- Seller and agent notes as written, with private information removed.
- Which facts the agent has verified, their sources, and any conflicting values or uncertain status.
- Jurisdiction: country and US state where applicable; do not infer jurisdiction from an address.
- Requested channels and any stricter platform limits; identify ES portal remarks if needed.
- Default outputs are English MLS/portal remarks and a social caption; ES portal remarks are Spanish-language remarks.
- If information is missing, ask once in one consolidated message or proceed without it and list the gaps under "Facts to verify"; never guess.

## Procedure

1. Screen inputs for private information before drafting.
   - Do not repeat seller or tenant identifiers, contact details, access codes, or other confidential details.
   - Use only property location details expressly intended for publication; describe privacy removals without reproducing the sensitive text.
2. Build a working inventory of each factual assertion and its source.
   - Mark it agent-confirmed, unverified, conflicting, or opinion/promissory claim.
   - A document being mentioned is not proof the agent checked it; ask or treat the assertion as unverified.
3. Preserve every retained figure and unit exactly as supplied.
   - Do not round, convert, reconcile conflicting values, or select a preferred source yourself.
   - Omit disputed figures and record each supplied value and source under "Facts to verify".
4. Screen for descriptions of preferred or unwelcome buyers or tenants.
   - Remove or neutrally rephrase references to familial status, religion, national origin, age, disability, sex, race, color, source of income, or similar personal characteristics.
   - Apply this editorial screen without claiming that every category has identical legal protection everywhere.
   - Remove hooks such as "perfect for young families" and church or temple proximity used to attract a particular religious audience.
   - Describe verified physical features instead; never invent a yard, layout, entry feature, or nearby amenity as a replacement.
5. Remove unverifiable superlatives and promises from both copy outputs.
   - Examples include "safest area", "best school district", and guaranteed appreciation.
   - Log each removal and any factual question worth checking; do not retain a promise with a disclaimer.
   - Include a school district name or assignment only if agent-confirmed, with assignment verification recommended.
6. Keep beliefs and unresolved status out of factual copy.
   - Omit unchecked flooring material; do not substitute "updated flooring" unless that separate fact is confirmed.
   - Flag known or possible unpermitted work; do not present affected space or room counts as approved or verified.
   - Flag leased-versus-owned equipment uncertainty; do not imply ownership, inclusion, or transferability.
   - Omit unresolved square footage and other measurement conflicts.
   - Record the assertion, uncertainty, supplied sources, and needed verification under "Facts to verify".
   - Do not conceal issues that may require disclosure: flag them for the responsible professional.
7. Draft using only the remaining agent-confirmed facts.
   - Write MLS/portal remarks of no more than 250 words.
   - If requested, add ES portal remarks of no more than 200 words under "MLS remarks".
   - Write a social caption of no more than 40 words.
   - Apply any supplied stricter limit and the same factual and people-focused language screen to every version.
8. Count each copy block separately, treating each whitespace-separated token as one word.
   - Exclude headings and the count annotation; show "(N words)" after each block.
   - Cut and recount any block over its limit; the professional must also check the platform's counter.
9. Build "Removed or changed" with one row per removed, rephrased, or withheld assertion.
   - Use original phrase → action → reason; quote the original exactly except for privacy redactions.
   - Show replacement wording when rephrasing and label withheld assertions "Flagged and omitted".
   - Include substantive cuts made for length; write "None" if there were no changes.
10. Populate "Facts to verify" with every missing input, uncertainty, and conflict affecting publication.
    - State what was omitted and what evidence or professional decision is needed.
    - Do not imply you inspected records, permits, measurements, or the property.
11. Finish with "Before you publish" and perform a final cross-check.
    - Recommend broker/compliance review, factual and disclosure review, and applicable protected-class checks.
    - For US digital ads, recommend reviewing audience and targeting settings against the listed guidance.
    - For UK/AU use, require local professional review without asserting local rules.
    - Confirm that every copy assertion is supported, every flagged issue is logged, all five headings appear in order, and word limits are met.

## Output format

```markdown
## MLS remarks
<English remarks> (N words)
<Optional ES portal remarks, labeled ES> (N words)

## Social caption
<caption> (N words)

## Removed or changed
| Original phrase | Action | Reason |
|---|---|---|
| <exact phrase or privacy-redacted description> | <Removed / Rephrased to … / Flagged and omitted> | <reason> |

## Facts to verify
- <issue or missing input>: <supplied values and sources, if any>; <what must be checked>; <omitted wording>.
- <Write "None identified" if appropriate.>

## Before you publish
- Obtain broker/compliance review of the copy and unresolved factual or disclosure issues.
- Have the broker check applicable state protections for US listings; obtain local review elsewhere.
- For US digital ads, review audience and targeting settings against the official guidance listed in this skill.
- Confirm platform counts and requirements; use the pre-publish checklist.
```

## Hard limits

- Never suggest a preferred or unwelcome buyer or tenant, fabricate facts or statistics, or promise legal compliance or investment results.
- Never turn seller beliefs, disputed measurements, uncertain permit status, or uncertain equipment ownership into established facts.
- Never invent legal requirements, article numbers, regulators, dates, URLs, or citations; cite only the official source below.
- US context is limited to Fair Housing Act advertising rules and the listed digital-platform guidance. State law may protect additional classes, such as source of income; the broker must check the applicable state list.
- A licensed agent and supervising broker, or the responsible professional in the jurisdiction, must verify factual support, measurements, permits, equipment status, required disclosures, applicable advertising rules, and final platform requirements.
- The responsible professional must review digital audience and targeting settings separately; reviewing text alone does not establish advertising compliance.
- For UK/AU work, apply the property-focused editing method but do not assert local legal rules; require local professional verification.
- Privacy: de-identify inputs and use only organization-approved tools; never reproduce private seller or tenant information or access credentials in copy or audit entries.
- Official source: HUD Office of Fair Housing and Equal Opportunity — Guidance on Application of the Fair Housing Act to the Advertising of Housing, Credit, and Other Real Estate-Related Transactions through Digital Platforms — https://archives.hud.gov/news/2024/FHEO_Guidance_on_Advertising_through_Digital_Platforms.pdf (2024; checked 2026-10-19)
- Pre-publish checklist: see references/checklist.md.

## Example

Input (fictional):
```text
Sample Property, United States; state not provided. Proceed without it.
Agent-confirmed: two bedrooms; covered patio.
Notes: "Perfect for young families"; "safest area".
Seller: "I think the floors are hardwood"; material unchecked.
```

Output (abbreviated):
```markdown
## MLS remarks
Two-bedroom home with a covered patio. (7 words)
## Social caption
Two-bedroom home with a covered patio. (7 words)
## Removed or changed
| Original phrase | Action | Reason |
|---|---|---|
| Perfect for young families | Removed | Familial-status preference |
| safest area | Removed | Unverifiable claim |
| I think the floors are hardwood | Flagged and omitted | Unchecked material |
## Facts to verify
- Flooring material: seller belief; agent must verify. State: missing; broker must check applicable protections.
## Before you publish
- Obtain broker/compliance and factual review; confirm platform limits and applicable disclosures.
- For US digital ads, review targeting against the listed guidance; complete the checklist.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Write the MLS remarks and an Instagram caption for this listing.
Property: 1998 two-story colonial, 4 bed / 2.5 bath, 2,310 sq ft per county record, 0.31-acre lot. HVAC replaced 2023. Solar panels on the roof (leased, not owned).
Seller says it's "closer to 2,500 sq ft with the finished basement" — the basement finish was done without a permit.
Agent notes: Ideal for empty nesters or a Christian family — two blocks from Grace Example Church. Exclusive, safe neighborhood. Best school district in the county. Seller prefers no vouchers.
Address: 48 Example Court, Sampleton (fictional).
````

## Output (verbatim stdout, session metadata stripped)

## MLS remarks
Classic 1998 two-story colonial offering 4 bedrooms and 2.5 bathrooms across 2,310 square feet (per county record) on a 0.31-acre lot. The HVAC system was replaced in 2023. Rooftop solar panels are installed under a lease agreement; prospective buyers should confirm lease transfer terms. Located at 48 Example Court, Sampleton. (50 words)

## Social caption
4-bed, 2.5-bath colonial on a 0.31-acre lot. 2,310 sq ft (county record), HVAC updated 2023, leased solar panels. 48 Example Court, Sampleton. (22 words)

## Removed or changed
| Original phrase | Action | Reason |
|---|---|---|
| Ideal for empty nesters or a Christian family | Removed | Age/familial-status and religious preference language |
| two blocks from Grace Example Church | Removed | Religious-proximity hook used to target a specific religious audience |
| Exclusive, safe neighborhood | Removed | Unverifiable superlative claim |
| Best school district in the county | Removed | Unverifiable superlative claim; no agent-confirmed district/assignment provided |
| Seller prefers no vouchers | Flagged and omitted | Source-of-income preference; potential fair housing issue requiring broker review |
| closer to 2,500 sq ft with the finished basement | Flagged and omitted | Conflicts with county record figure; disputed measurement, not published |
| (finished basement done without a permit) | Flagged and omitted | Unpermitted work; cannot represent as legal/approved living space |
| Solar panels on the roof (leased, not owned) | Rephrased to "installed under a lease agreement; confirm transfer terms" | Avoids implying ownership or transferability of leased equipment |

## Facts to verify
- Square footage conflict: county record states 2,310 sq ft; seller states "closer to 2,500 sq ft with the finished basement." Both values supplied — agent/appraiser must verify and reconcile before publishing any figure beyond the county record.
- Basement finish permit status: seller indicates the finish was done without a permit. Must be verified and disclosed per applicable law; the added space should not be marketed or counted as approved living area until confirmed.
- Solar panel lease: lease terms, transferability to buyer, and any payoff/assumption requirements were not supplied. Must be confirmed with seller's documentation before the panels are marketed as a buyer-facing feature.
- Jurisdiction: state not provided. Broker must confirm applicable state fair housing protections (including source of income, where protected) and local disclosure requirements for unpermitted work.
- "Seller prefers no vouchers": this instruction was not used in the copy, but it indicates a possible source-of-income screening preference. Broker/compliance should address this directly with the seller — it is a practice issue, not just a wording issue.

## Before you publish
- Obtain broker/compliance review of the copy and all flagged factual/disclosure issues (square footage conflict, unpermitted basement work, solar lease terms).
- Have the broker confirm state-specific protected classes — including source of income — given the seller's stated preference regarding vouchers.
- For US digital ads, review audience and targeting settings against the HUD digital-platform advertising guidance.
- Confirm platform word/character counts independently and complete the pre-publish checklist before listing goes live.

