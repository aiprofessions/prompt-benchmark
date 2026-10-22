---
name: event-planners-vendor-rfp
description: "Use when an event planner pastes an event brief and requests a vendor RFP; returns a vendor-facing draft with exact requirements, itemized pricing, deadlines, and missing items marked TBD."
---

# Vendor RFP Builder for Events

## What it does

Drafts a vendor request for proposal (RFP) from an event brief. Preserves the brief's counts, dates, times, technical requirements, and venue constraints. Requests comparable pricing and vendor documents, while marking missing information TBD for the planner to resolve before sending.

## Inputs it expects

- Client/event name, planner or agency, and approved contact details.
- Event date(s), venue name/address, and headcount.
- Dietary and allergy counts, without guest names or individual health records.
- Services, equipment, quantities, and technical specifications.
- Schedule, including load-in, setup, service, strike, and load-out.
- Venue constraints, including kitchen limits, house rigging, and access.
- Budget, insurance requirements, and other client requirements, if supplied.
- Response deadline, decision date, questions deadline, and evaluation criteria.

Proceed with missing fields marked TBD and list them under Open items (TBD); never guess.
If the user requests clarification before drafting, ask one grouped question, then use TBD for anything still unanswered.

## Procedure

1. Extract the supplied facts and requested service categories. Use one combined RFP unless the brief requests separate RFPs; separate the scope and pricing by category.
2. Copy every count, date, time, quantity, and technical requirement exactly as written, including dietary/allergy counts and load-in/out. Do not convert units, normalize date/time formats, round, calculate totals, or silently correct values.
3. Check for conflicting statements and apparently inconsistent counts. Do not assume dietary categories are mutually exclusive or allergies are additional guests. Preserve the supplied statements and flag the interpretation or conflict under Open items (TBD).
4. Draft scope only from the requested services and requirements. Set absent budget, contacts, dates, venue capabilities, and other event facts to TBD. Do not infer facilities or equipment from a venue's name or the requested service.
5. Put every supplied venue constraint under Venue constraints as "Vendor must plan around: [exact constraint]." Include kitchen limits, house rigging, and access restrictions when supplied. For missing constraints, write TBD and request planner confirmation with the venue.
6. When food service, allergies, or dietary restrictions appear, request the vendor's allergen-handling and cross-contact procedure in writing. Ask it to address labeling, preparation controls, staff briefing, meal identification without guest names, and any handling limitations. Do not promise an allergen-free outcome.
7. Require a pricing table with a separate line for each service and equipment item, labor, delivery, service charge, tax, and gratuity. Add separate setup/strike lines when separately charged. Request quantities, rates, amounts, and the basis for charges; require vendors to mark estimates and explicitly identify included or inapplicable charges rather than omit them.
8. Request a certificate of insurance and the vendor's deposit schedule, cancellation/postponement terms, and payment terms. Copy supplied coverage requirements exactly; otherwise mark coverage types/limits TBD. Request only permit/license types identified in the brief; put unresolved documentation requirements in Open items (TBD).
9. State the response deadline and decision date exactly as supplied, or TBD. Include a questions deadline if supplied; otherwise mark it TBD. Copy supplied evaluation criteria and weights without adding criteria, rankings, or weights; mark missing criteria TBD.
10. Produce the eight sections in the Output format order. Replace template instructions with brief facts, vendor requests, or TBD. Pricing cells awaiting a vendor quote must say "Vendor to quote," not contain invented amounts.
11. List every missing field and unresolved conflict under Open items (TBD), with a question for the planner. Distinguish vendor quote requests from missing planner facts; vendor quote requests do not need a TBD entry.
12. Audit the draft against the brief: check every figure, technical requirement, and constraint individually; verify all required pricing lines, documents, deadlines, criteria, and open items. Remove unsupported facts. If TBDs or conflicts remain, label the header "Draft — planner review required"; otherwise label it "For planner approval before sending."

## Output format

```markdown
## RFP header
- Request for proposal: [service categories]
- Status: [review status from Procedure]
- Issued by: [brief value or TBD]
- Contact: [approved name/email/phone from brief or TBD]
- Response deadline: [exact brief value or TBD]

## Event overview
- Client/event: [brief value or TBD]
- Event date(s): [exact brief value or TBD]
- Venue/address: [brief values or TBD]
- Headcount and breakdowns: [exact brief values or TBD]
- Schedule, including load-in/out: [exact brief values; missing fields TBD]
- Budget: [exact brief value or TBD]

## Scope and requirements
- [Requested services, quantities, and technical requirements exactly]
- [If applicable: exact dietary/allergy counts or TBD]
- [If applicable: submit written allergen-handling/cross-contact procedure,
  including controls, labeling, staff briefing, meal identification, and limitations]

## Venue constraints
- Vendor must plan around: [each exact supplied constraint]
- [Missing constraints: TBD — planner to confirm with venue]

## Pricing format
| Item | Quantity/hours | Unit rate/charge basis | Amount |
|------|----------------|------------------------|--------|
| [Each service, on its own line] | Vendor to quote | Vendor to quote | Vendor to quote |
| [Each equipment item, on its own line] | Vendor to quote | Vendor to quote | Vendor to quote |
| Labor, by role | Vendor to quote | Vendor to quote | Vendor to quote |
| Delivery | Vendor to quote | Vendor to quote | Vendor to quote |
| Service charge | Vendor to quote | Vendor to quote | Vendor to quote |
| Tax | Vendor to quote | Vendor to quote | Vendor to quote |
| Gratuity | Vendor to quote | Vendor to quote | Vendor to quote |
Add setup/strike lines if separately charged. Do not bundle charges.
Identify estimates, included charges, and inapplicable charges explicitly.

## Vendor documents required
- Certificate of insurance; coverage types/limits: [exact brief values or TBD]
- Deposit schedule; cancellation/postponement terms; payment terms
- [Written allergen-handling/cross-contact procedure when applicable]
- [Permit/license documentation explicitly requested in the brief]

## Timeline and evaluation
- Questions deadline: [exact brief value or TBD]
- Response deadline: [exact brief value or TBD]
- Decision date: [exact brief value or TBD]
- Evaluation criteria and any supplied weights: [brief values or TBD]

## Open items (TBD)
- [Each missing fact or conflict] — [question for planner]
```

## Hard limits

- Never invent event facts, budgets, contacts, venue capabilities, dates, evaluation criteria, insurance limits, legal requirements, or statistics. Never change supplied figures or technical requirements.
- Request vendor terms; do not invent contractual commitments or describe the RFP as legally sufficient.
- Permits, alcohol service, food-safety, and venue rules are local. The responsible planner must confirm applicable requirements with the venue and local authority before use.
- The responsible planner must verify scope, counts, schedule, venue constraints, deadlines, evaluation criteria, and insurance requirements with the appropriate client, venue, or vendor representative before sending.
- The responsible planner must review the written allergen procedure with the food-service provider and venue; the skill cannot certify food safety or absence of cross-contact.
- Contract terms, including cancellation and deposit terms, need the client's or agency's legal review before signing.
- No official AI-specific guidance was verified for this profession. Check with the relevant licensing body or regulator, where applicable. Do not invent or cite sources, laws, regulators, URLs, or guidance dates.
- Use US terminology by default. For UK/AU work, retain brief terminology and require local professional verification; do not assert local tax, licensing, insurance, or legal rules.
- Privacy: de-identify client and guest information before processing, and use only tools approved for the data involved. Exclude guest names and individual health records; use necessary aggregate dietary/allergy counts. The planner restores approved contact details before sending.
- Before sending or signing, see references/checklist.md.

## Example

Fictional input:
```text
Client: Sample Event; venue: Example Hall; service: dinner catering.
Headcount: 40; 2 guests with peanut allergy.
Load-in: 2:00 PM; load-out: 9:00 PM.
Venue constraints: warming kitchen only; no cooking on site.
```

Abbreviated output (full output uses the template above):
```text
## RFP header
Draft — planner review required; Sample Event; contact/response deadline: TBD.
## Event overview
Example Hall; headcount: 40; load-in: 2:00 PM; load-out: 9:00 PM; date: TBD.
## Scope and requirements
Dinner catering; 2 guests with peanut allergy; submit written allergen-handling/cross-contact procedure.
## Venue constraints
Vendor must plan around: warming kitchen only; no cooking on site.
## Pricing format
Separate lines: each service/equipment item, labor, delivery, service charge, tax, gratuity; vendor to quote.
## Vendor documents required
Certificate of insurance; deposit schedule; cancellation/postponement and payment terms; written allergen procedure.
## Timeline and evaluation
Response deadline, decision date, questions deadline, and evaluation criteria: TBD.
## Open items (TBD)
Confirm issuer/contact, date, address, remaining schedule, budget, coverage requirements, deadlines, and criteria.
```
