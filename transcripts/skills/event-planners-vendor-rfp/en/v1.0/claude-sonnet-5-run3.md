# Transcript — skill event-planners-vendor-rfp [en] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:13:44+00:00
- duration_s: 38.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c4a9629f8e15385f7fb80cf0168ef081201eec103279521fae4d1d1d66b3c488
- skill_sha256: 3c25f94a1a7932aff88dfc2e5eefc8d19e74871ef9644eead608b49a55726afd

## Query (verbatim, from query file)

````text
<skill_instructions>
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
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Build the AV vendor RFP from this brief.
Client: Sample Foundation (fictional) — annual gala. Date: Saturday, April 24, 2027.
Venue: Example Hotel Grand Ballroom, Austin, TX (fictional). House rigging points available, but the venue requires its in-house rigger for any rigging. Load-in from 07:00; load-out complete by 01:00.
Guests: 350 at 35 rounds of 10. Program 18:30–22:30: welcome, 3 speakers, a 6-minute video, live auction, band 21:00–22:30 (band brings its own backline).
AV needs: stage 24 ft x 12 ft x 2 ft high; 2 projection screens; 4 wireless handheld mics + 2 lavaliers; confidence monitor for speakers; livestream of the speeches only (not the auction).
Proposals due February 1, 2027. Decision by February 12, 2027.
````

## Output (verbatim stdout, session metadata stripped)

RFP header
Request for proposal: Audio-Visual (AV) production services
Status: Draft — planner review required
Issued by: TBD
Contact: TBD
Response deadline: February 1, 2027

Event overview
Client/event: Sample Foundation — annual gala
Event date(s): Saturday, April 24, 2027
Venue/address: Example Hotel Grand Ballroom, Austin, TX
Headcount and breakdowns: 350 guests at 35 rounds of 10
Schedule, including load-in/out:
  Load-in: 07:00
  Program: 18:30–22:30 (welcome, 3 speakers, 6-minute video, live auction, band 21:00–22:30)
  Load-out complete by: 01:00
Budget: TBD

Scope and requirements
- Staging: 1 stage, 24 ft x 12 ft x 2 ft high
- Projection: 2 projection screens
- Microphones: 4 wireless handheld microphones; 2 lavalier microphones
- Confidence monitor for speakers (quantity as stated: 1)
- Livestream of the speeches only (welcome and 3 speakers); auction is not to be livestreamed
- Video playback support for a 6-minute video during program
- Band performs 21:00–22:30; band brings its own backline — vendor to specify what sound reinforcement/mixing, if any, it will provide for the band versus what the band supplies
- Not applicable: no dietary/allergy requirements identified for this AV scope

Venue constraints
- Vendor must plan around: house rigging points are available, but the venue requires its own in-house rigger for any rigging — vendor must coordinate scope/cost with venue's in-house rigger and may not supply its own rigger for rigging work
- Power availability/distribution at stage and FOH: TBD — planner to confirm with venue
- Internet/network connectivity for livestream at venue: TBD — planner to confirm with venue
- Loading dock/freight elevator access for load-in/load-out: TBD — planner to confirm with venue
- Ceiling height/sightline or house drape constraints for 24 ft x 12 ft stage and 2 screens: TBD — planner to confirm with venue

Pricing format
Item                              Quantity/hours   Unit rate/charge basis   Amount
Stage (24 ft x 12 ft x 2 ft)      Vendor to quote  Vendor to quote          Vendor to quote
Projection screens (2)            Vendor to quote  Vendor to quote          Vendor to quote
Projectors (if required)          Vendor to quote  Vendor to quote          Vendor to quote
Wireless handheld mics (4)        Vendor to quote  Vendor to quote          Vendor to quote
Lavalier mics (2)                 Vendor to quote  Vendor to quote          Vendor to quote
Confidence monitor                Vendor to quote  Vendor to quote          Vendor to quote
Audio mixing/PA for program        Vendor to quote  Vendor to quote          Vendor to quote
Sound reinforcement for band (specify what is additive to band's own backline) Vendor to quote Vendor to quote Vendor to quote
Livestream production (speeches only — encoding, platform delivery, operator) Vendor to quote Vendor to quote Vendor to quote
Video playback support (6-min video) Vendor to quote Vendor to quote        Vendor to quote
Labor, by role                    Vendor to quote  Vendor to quote          Vendor to quote
Delivery                          Vendor to quote  Vendor to quote          Vendor to quote
Setup/strike (if separately charged) Vendor to quote Vendor to quote        Vendor to quote
Service charge                    Vendor to quote  Vendor to quote          Vendor to quote
Tax                               Vendor to quote  Vendor to quote          Vendor to quote
Gratuity                          Vendor to quote  Vendor to quote          Vendor to quote

Vendor must explicitly identify which charges above are included, which are inapplicable, and which are estimates. Do not bundle line items.

Vendor documents required
- Certificate of insurance; coverage types/limits: TBD
- Deposit schedule; cancellation/postponement terms; payment terms
- Written confirmation of how vendor will coordinate with the venue's required in-house rigger (scope split and any additional rigger fees)
- Permit/license documentation: none identified in brief; planner to confirm with venue whether any are required

Timeline and evaluation
Questions deadline: TBD
Response deadline: February 1, 2027
Decision date: February 12, 2027
Evaluation criteria and any supplied weights: TBD

Open items (TBD)
- Issuer name and approved contact (name/email/phone) for this RFP — who should vendors send proposals and direct questions to?
- Budget — is there a budget ceiling or range to share with vendors?
- Questions deadline — by what date must vendor questions be submitted?
- Evaluation criteria and weights — how will proposals be scored (price, experience, references, etc.)?
- Insurance coverage types and limits — what does the venue or client require?
- Power availability/distribution — confirm with venue what power is available at stage/FOH or must be vendor-supplied.
- Internet/network connectivity for the livestream — confirm with venue, or will vendor supply cellular/satellite backup?
- Livestream destination/platform — where should the speeches stream be delivered (e.g., private link, public platform)? Not specified in brief.
- Loading dock/freight elevator/access restrictions for load-in and load-out — confirm with venue.
- Ceiling height, sightlines, or house drape that could affect the 24 ft x 12 ft stage or 2 projection screens — confirm with venue.
- Sound reinforcement scope for the band — brief states band brings its own backline but does not specify whether vendor provides FOH mixing, additional monitors, or PA; confirm with client/band.
- Rigging cost responsibility — brief states venue requires its own in-house rigger; confirm whether the venue's rigger fee is billed to the client directly or should be included in vendor's quote.

The responsible planner must verify all scope, schedule, venue constraints, deadlines, evaluation criteria, and insurance requirements with the client, venue, and vendors before sending this RFP, and have any resulting contract terms reviewed by the client's/agency's legal counsel before signing.

