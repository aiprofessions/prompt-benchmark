# Transcript — skill real-estate-compliant-listing [en] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:36:07+00:00
- duration_s: 58.7
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 9925732aa90f3483d1fb4354a85ae98bc82422c0cf4e5dc513ecc0c31b48a0bc
- skill_sha256: e70b77c16dab34efb9d8a307d5a086214c95a5f18cbd7234abd59916f240e0ef

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: real-estate-compliant-listing
description: "Use when an agent pastes property facts and rough notes to get property-focused listing copy, a social caption, and an audit list for professional review."
---

# Fair-Housing-Safe Listing Copy

## What it does

Turns property facts and seller or agent notes into property-focused listing copy and a social caption. Removes preferred-buyer language, unsupported claims, and unverified assertions. Retains documented figures with source attribution when seller claims conflict with them. Provides an audit list for professional review, not a certification of legal compliance.

## Inputs it expects

- Property facts intended for publication: location, price, bedrooms, bathrooms, area, fees, features, and included equipment.
- Seller and agent notes as written, with private information removed.
- Agent-confirmed facts, supporting sources, documented figures, conflicting values, and uncertain status.
- Jurisdiction: country and US state where applicable; do not infer jurisdiction from an address.
- Target portals, requested language, and stricter platform limits; identify any request labeled "ES portal".
- Default to English MLS/portal remarks and a social caption. Do not infer a language from "ES portal"; confirm the portal and language or flag them as missing.
- Ask once in one consolidated message for missing information, or proceed and list the gaps under "Facts to verify"; never guess.

## Procedure

1. Screen inputs for private information before drafting.
   - Do not reproduce seller or tenant identifiers, contact details, access codes, or confidential information.
   - Use location details only when expressly intended for publication; describe privacy removals without quoting sensitive text.
2. Inventory each factual assertion and its supplied support.
   - Mark it agent-confirmed, documented, unverified, conflicting, or opinion/promissory claim.
   - Treat a figure supplied with an identified public record, survey, or appraisal as documented for drafting, subject to professional verification.
   - A seller's unsupported reference to a document is not documentation; request the figure and source or flag it as unverified.
3. Preserve retained figures and units exactly as supplied.
   - Do not round, convert, average, or silently reconcile values.
   - Agent-confirmed facts such as prices and room counts do not require a public record solely because they contain numbers.
4. Resolve documented-figure conflicts before drafting.
   - When a public record, survey, or appraisal figure conflicts with a seller claim, state the documented figure in MLS/portal remarks with its source, such as "1,480 sq ft per county record".
   - Retain that documented figure in every requested portal version, including ES portal remarks; never drop it because the seller claims a different value or to meet a word limit.
   - Never state the seller's conflicting figure as fact. Log its replacement under "Removed or changed".
   - Put both values, their supplied sources, and the verification needed under "Facts to verify".
   - If documented sources disagree, state each figure with its source rather than choosing or averaging; flag the conflict.
   - For an uncertain or conflicting measurement, omit the figure only if no documented value exists; list the supplied claims for verification.
   - A social caption may omit measurements for brevity; if it includes a disputed measurement, use the documented figure with its source.
5. Screen for preferred or unwelcome buyers or tenants.
   - Remove or neutrally rephrase references to familial status, religion, national origin, age, disability, sex, race, color, source of income, or similar personal characteristics.
   - Apply this editorial screen without claiming all categories have identical legal protection everywhere.
   - Remove hooks such as "perfect for young families" and church or temple proximity used to attract a religious audience.
   - Describe supported physical features instead; never invent replacement features or amenities.
6. Remove unverifiable superlatives and promises from every copy version.
   - Remove claims such as "safest area", "best school district", and guaranteed appreciation; a disclaimer does not make them acceptable.
   - Log each removal and any factual question worth checking.
   - Include school district names or assignments only if agent-confirmed, and recommend assignment verification.
7. Keep seller beliefs and unresolved status out of factual copy.
   - Omit unchecked flooring material; do not replace it with "updated flooring" unless that separate fact is confirmed.
   - Flag known or possible unpermitted work; do not describe affected space or room counts as approved or verified.
   - Flag uncertain equipment ownership or lease status; do not imply ownership, inclusion, or transferability.
   - Apply step 4 to square footage and other measurement conflicts.
   - List each uncertainty, supplied support, and needed verification under "Facts to verify".
   - Flag possible disclosure issues for professional review; omission from advertising does not resolve disclosure obligations.
8. Draft only from agent-confirmed facts and documented figures, retaining source attribution for documented figures.
   - Keep MLS/portal remarks at or below 250 words.
   - Keep any requested ES portal remarks at or below 200 words under "MLS remarks", labeled by portal and confirmed language.
   - Keep the social caption at or below 40 words.
   - Apply stricter supplied limits and the same factual and personal-characteristic screens to every version.
9. Count each copy block using whitespace-separated tokens.
   - Exclude headings and count annotations; show "(N words)" after each block.
   - Cut and recount over-limit blocks without removing required documented-conflict figures or their attribution.
   - If required content cannot fit a supplied limit, flag the conflict and request a professional decision; do not label an over-limit block ready to publish.
10. Build "Removed or changed" with one entry per removed, rephrased, replaced, or withheld assertion.
    - Use original phrase → action → reason; quote exactly except for privacy redactions.
    - Include replacement wording and substantive length cuts; label withheld assertions "Flagged and omitted".
    - Write "None" if no changes were needed.
11. Populate "Facts to verify" with all publication-relevant gaps, uncertainties, and conflicts.
    - Identify omitted wording or the documented figure used, supplied sources, and evidence or professional decisions needed.
    - Do not imply you inspected records, permits, measurements, or the property.
12. Complete "Before you publish" and cross-check the response.
    - Recommend broker/compliance review, factual and disclosure review, and applicable protected-class checks.
    - For US listings, require the broker to check the applicable state list; for US digital ads, recommend separate audience and targeting review against the listed guidance.
    - For UK/AU use, require local professional review without asserting local rules.
    - Check every copy assertion against the inventory, every required documented figure against each portal version, and every change against the audit list.
    - Confirm all five output headings appear in order and all word counts meet their limits.

## Output format

```markdown
## MLS remarks
<English remarks; retain documented-conflict figures with source attribution.> (N words)
<Optional ES portal version, labeled by portal and confirmed language.> (N words)

## Social caption
<Caption.> (N words)

## Removed or changed
- "<Original phrase or privacy-redacted description>" → <action and replacement, if any> → <reason>.
- <Use "None" if no changes were needed.>

## Facts to verify
- <Issue or missing input>: <supplied values and sources>; <wording omitted or documented figure used>; <verification needed>.
- <Use "None identified" if appropriate.>

## Before you publish
- Obtain broker/compliance review of copy, factual support, and unresolved disclosure issues.
- Have the broker check applicable US state protections; obtain local professional review elsewhere.
- For US digital ads, review audience and targeting settings against the official guidance listed in this skill.
- Check platform counts and requirements; complete references/checklist.md.
```

## Hard limits

- Never describe an ideal buyer or tenant, fabricate facts or statistics, or promise legal compliance or investment results.
- Never turn seller beliefs, conflicting seller claims, uncertain permits, or uncertain equipment status into established facts.
- Never omit a documented figure from portal remarks because a seller disputes it; attribute it and flag the conflict.
- Never invent laws, article numbers, regulators, dates, URLs, or citations; cite only the official source below.
- US context is limited to Fair Housing Act advertising rules and the listed digital-platform guidance. State law may protect additional classes, such as source of income; the broker must check the applicable state list.
- A licensed agent and supervising broker, or the responsible professional in the jurisdiction, must verify facts, measurements, permits, equipment status, required disclosures, applicable advertising rules, and final platform requirements before publication.
- The responsible professional must separately verify digital audience and targeting settings; text review alone does not establish advertising compliance.
- For UK/AU work, use the property-focused editing method without asserting local rules; require local professional verification.
- Privacy: de-identify inputs and use only organization-approved tools; never reproduce private seller or tenant information or access credentials in copy or audit entries.
- Official source: HUD Office of Fair Housing and Equal Opportunity — Guidance on Application of the Fair Housing Act to the Advertising of Housing, Credit, and Other Real Estate-Related Transactions through Digital Platforms — https://archives.hud.gov/news/2024/FHEO_Guidance_on_Advertising_through_Digital_Platforms.pdf (2024; checked 2026-10-19)
- Pre-publish checklist: see references/checklist.md.

## Example

Input (fictional):
```text
Sample Property, United States; state not provided. Proceed without it.
Agent-confirmed: two bedrooms; covered patio. County record (agent-supplied): 1,480 sq ft.
Notes: "Perfect for young families"; "safest area".
Seller: "It's 1,700 sq ft".
Seller: "I think the floors are hardwood"; material unchecked.
```

Output (abbreviated):
```markdown
## MLS remarks
Two-bedroom home with a covered patio; 1,480 sq ft per county record. (12 words)
## Social caption
Two-bedroom home, covered patio, 1,480 sq ft per county record. (10 words)
## Removed or changed
- "Perfect for young families" → Removed → Familial-status preference.
- "safest area" → Removed → Unverifiable claim.
- "It's 1,700 sq ft" → Replaced with "1,480 sq ft per county record" → Documented figure controls drafting.
- "I think the floors are hardwood" → Flagged and omitted → Unchecked material.
## Facts to verify
- Area: county record 1,480 sq ft used; seller claims 1,700 sq ft. Verify discrepancy and source.
- Flooring omitted: verify material. State missing: obtain it for the broker's protected-class check.
## Before you publish
- Obtain broker/compliance, factual, and disclosure review; check state protections, digital-ad targeting, and platform counts using the checklist.
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
Charming 1998 two-story colonial at 48 Example Court, Sampleton. 4 bedrooms, 2.5 bathrooms, 2,310 sq ft per county record, on a 0.31-acre lot. HVAC system replaced in 2023. Rooftop solar panels are leased, not owned; buyer should confirm lease terms and transferability. Classic colonial architecture with comfortable living spaces throughout. Contact listing agent for showing details and full property information. (60 words)

## Social caption
1998 two-story colonial, 4 bed/2.5 bath, 2,310 sq ft per county record, 0.31-acre lot. HVAC replaced 2023. Leased solar panels on roof. Schedule your showing today! (26 words)

## Removed or changed
- "Ideal for empty nesters or a Christian family" → Removed → Familial-status and religious preference.
- "two blocks from Grace Example Church" → Removed → Religious-proximity hook used to attract a specific faith audience.
- "Exclusive, safe neighborhood" → Removed → Unverifiable superlative claim.
- "Best school district in the county" → Removed → Unverifiable superlative; no agent-confirmed district name or assignment supplied.
- "Seller prefers no vouchers" → Removed → Source-of-income preference; serious fair-housing exposure, flagged for mandatory broker review.
- "closer to 2,500 sq ft with the finished basement" → Replaced with "2,310 sq ft per county record" in all copy → Documented figure controls over seller's conflicting, unverified claim.
- Finished-basement square footage/room description → Flagged and omitted → Basement finish done without permit; cannot be described as approved livable space or counted toward totals.

## Facts to verify
- Square footage: county record states 2,310 sq ft (used in all copy); seller claims "closer to 2,500 sq ft with the finished basement." Verify discrepancy and confirm whether any basement area can ever be counted as legal living space.
- Basement finish: reported as done without permit. Confirm permit status, code compliance, and any required seller disclosure before this space is referenced in marketing or disclosure documents.
- Solar panels: leased, not owned. Confirm lease holder, remaining term, transfer/assumption process, and whether lender or lease-company approval is needed before describing to buyers.
- Jurisdiction: country/state not supplied. Required before the broker can run the state-level protected-class check, particularly given the voucher instruction below.
- "No vouchers" instruction: flag to broker/compliance immediately. Source-of-income discrimination is prohibited in many states and localities, and the instruction itself (even if never published) may create liability exposure the broker needs to address with the seller.
- School district: no agent-confirmed district name or assignment supplied; omitted from copy pending verification.
- Address: 48 Example Court, Sampleton used as supplied; confirm it's approved for public-facing listing use.

## Before you publish
- Obtain broker/compliance review of this copy, the factual inventory above, and the unresolved basement-permit and solar-lease issues.
- Flag the "no vouchers" instruction to the broker now — this needs handling at the seller-management level, not just an advertising edit, and the broker must check the applicable state's source-of-income and other protected-class rules.
- For any US digital ad placement, separately review audience and targeting settings against HUD's 2024 Digital Platforms guidance; text compliance alone doesn't cover targeting.
- Verify platform word/character limits and complete the pre-publish checklist before posting.

