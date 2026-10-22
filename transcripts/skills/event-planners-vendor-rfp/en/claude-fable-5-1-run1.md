# Transcript — skill event-planners-vendor-rfp [en] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:26:26+00:00
- duration_s: 44.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: c4a9629f8e15385f7fb80cf0168ef081201eec103279521fae4d1d1d66b3c488
- skill_sha256: 3b6da89ddf3fb21f976faf74270b77a1f6e008ab6c0ce75f6220f0c8bd65791d

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: event-planners-vendor-rfp
description: "Use when an event planner pastes an event brief and requests a vendor RFP; returns a draft with exact requirements, separate pricing lines, deadlines, and open items."
---

# Vendor RFP Builder for Events

## What it does

Drafts a vendor request for proposal (RFP) from an event brief. Preserves supplied counts, dates, times, technical requirements, and venue constraints while requesting comparable pricing and vendor documents. Marks missing event facts TBD and, when evaluation criteria are absent, proposes a short set for client approval before sending.

## Inputs it expects

- Client/event name, planner or agency, and approved business contact details.
- Event date(s), venue name/address, and headcount.
- Aggregate dietary and allergy counts, without guest names or individual health records.
- Services, equipment, quantities, and technical specifications.
- Schedule, including load-in, setup, service, strike, and load-out.
- Venue constraints, including kitchen limits, house rigging, and access.
- Budget, insurance requirements, and other client requirements, if supplied.
- Response deadline, decision date, questions deadline, and evaluation criteria.

Proceed with missing facts marked TBD and list them under Open items (TBD); never guess.
If clarification is requested before drafting, ask one grouped question, then mark unanswered facts TBD.
Missing evaluation criteria are the sole exception: use the labeled proposal in Procedure step 10.

## Procedure

1. Extract supplied facts and requested service categories. Use one combined RFP unless separate RFPs are requested; separate scope and pricing by category. Exclude guest identifiers and individual health records from the output.
2. Copy every count, date, time, quantity, and technical requirement exactly as written, including dietary/allergy counts and load-in/out. Do not convert units, normalize date/time formats, round, calculate new totals, or silently correct values.
3. Check for conflicts and apparently inconsistent counts. Do not assume dietary categories are mutually exclusive or allergies are additional guests. Preserve conflicting statements and flag each conflict with a question under Open items (TBD).
4. Draft scope only from requested services and requirements. Set absent budget, contacts, dates, venue capabilities, and other event facts to TBD. Do not infer facilities or equipment from a venue name or requested service.
5. Put every supplied venue constraint under Venue constraints as "Vendor must plan around: [exact constraint]." Include kitchen limits, house rigging, and access restrictions when supplied. Mark missing constraint information TBD and request planner confirmation with the venue.
6. When food service, allergies, or dietary restrictions appear, request the vendor's allergen-handling and cross-contact procedure in writing. Ask for labeling, preparation controls, staff briefing, meal identification without guest names, and handling limitations. Do not promise an allergen-free outcome.
7. Require a separate pricing line for each service, each equipment item, labor, delivery, service charge, tax, and gratuity. Add setup/strike lines if separately charged. Preserve supplied quantities, rates, and amounts exactly; mark unsupplied quote cells "Vendor to quote." Request quantities, rates, amounts, and charge bases. Require estimates, included charges, and inapplicable charges to be identified explicitly.
8. Request a certificate of insurance, deposit schedule, cancellation/postponement terms, and payment terms. Copy supplied coverage requirements exactly; otherwise mark coverage types/limits TBD. Request permit/license types only when identified in the brief; list unresolved documentation requirements under Open items (TBD).
9. State the response deadline and decision date exactly as supplied, or TBD. Include a questions deadline if supplied; otherwise mark it TBD.
10. If evaluation criteria are supplied, copy them and any weights exactly without adding, ranking, or weighting. Otherwise insert "Proposed evaluation criteria — confirm with the client before sending" followed by: compliance with stated requirements; completeness and clarity of itemized pricing; relevant experience and references; operational plan for the venue constraints; allergen-handling/safety procedures when food, dietary, or allergy items appear; insurance and terms. Add no weights or rankings. Never leave absent criteria merely TBD. Add an Open items question asking the client to confirm or edit the proposed criteria.
11. Request evidence supporting each evaluation criterion under Vendor documents required, including relevant experience/references and a venue operational plan when those criteria are used. Do not invent minimum experience, reference counts, certifications, or scoring thresholds.
12. Produce the eight sections in the Output format order. Replace template instructions with supplied facts, vendor requests, or TBD. Distinguish missing planner facts from information vendors must supply; vendor quote requests do not need TBD entries.
13. List every missing planner fact and unresolved conflict under Open items (TBD), each with a question. Audit every figure, technical requirement, and venue constraint against the brief. Verify all pricing lines, documents, deadlines, and criteria; remove unsupported facts.
14. If TBDs, conflicts, or proposed criteria remain, label the header "Draft — planner review required"; otherwise use "For planner approval before sending." Do not describe proposed criteria as approved. Require the planner to obtain client approval and replace the proposed label with approved criteria before release.

## Output format

```markdown
## RFP header
- Request for proposal: [service categories]
- Status: [review status from Procedure]
- Issued by: [brief value or TBD]
- Contact: [approved business contact details from brief or TBD]
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
- [If applicable: submit written allergen-handling/cross-contact procedure
  addressing controls, labeling, staff briefing, meal identification, and limitations]

## Venue constraints
- Vendor must plan around: [each exact supplied constraint]
- [Missing constraint information: TBD — planner to confirm with venue]

## Pricing format
[In every cell, retain supplied values exactly; otherwise use "Vendor to quote."]
| Item | Quantity/hours | Unit rate/charge basis | Amount |
|------|----------------|------------------------|--------|
| [Each service, on its own line] | [Value] | [Value] | [Value] |
| [Each equipment item, on its own line] | [Value] | [Value] | [Value] |
| Labor, by role | [Value] | [Value] | [Value] |
| Delivery | [Value] | [Value] | [Value] |
| Service charge | [Value] | [Value] | [Value] |
| Tax | [Value] | [Value] | [Value] |
| Gratuity | [Value] | [Value] | [Value] |
Add setup/strike lines if separately charged. Do not bundle charges.
Identify estimates, included charges, and inapplicable charges explicitly.

## Vendor documents required
- Certificate of insurance; coverage types/limits: [exact brief values or TBD]
- Deposit schedule; cancellation/postponement terms; payment terms
- [Written allergen-handling/cross-contact procedure when applicable]
- [Evidence supporting criteria, including experience/references and venue plan when used]
- [Permit/license documentation explicitly requested in the brief]

## Timeline and evaluation
- Questions deadline: [exact brief value or TBD]
- Response deadline: [exact brief value or TBD]
- Decision date: [exact brief value or TBD]
- [Use supplied evaluation criteria and weights exactly; otherwise use:]
  Proposed evaluation criteria — confirm with the client before sending:
  [Default set from Procedure step 10; no weights or rankings]

## Open items (TBD)
- [Each missing planner fact or conflict] — [question for planner]
- [If criteria proposed] Will the client confirm or edit these criteria before sending?
```

## Hard limits

- Never invent event facts, budgets, contacts, venue capabilities, dates, insurance limits, legal requirements, or statistics. Never change supplied figures or technical requirements.
- Proposed evaluation criteria are suggestions, not event facts or client approval. Use only the default set when criteria are absent; do not invent weights or rankings.
- Request vendor terms; do not invent contractual commitments or describe the RFP as legally sufficient.
- Permits, alcohol service, food-safety, and venue rules are local. The responsible planner must confirm applicable requirements with the venue and local authority.
- Before sending, the responsible planner must verify scope, counts, schedule, venue constraints, deadlines, evaluation criteria, and insurance requirements with the appropriate client, venue, or vendor representative.
- The responsible planner must review the written allergen procedure with the food-service provider and venue before service; this skill cannot certify food safety or absence of cross-contact.
- Contract terms, including cancellation and deposit terms, need the client's or agency's legal review before signing.
- No official AI-specific guidance was verified for this profession. Check with the relevant licensing body or regulator, where applicable. Do not invent or cite sources, laws, regulators, URLs, or guidance dates.
- Use US terminology by default. For UK/AU work, retain brief terminology and require local professional verification; do not assert local tax, licensing, insurance, or legal rules.
- Privacy: de-identify confidential client and guest information before processing; use only tools approved for the data involved. Exclude guest names and individual health records; use necessary aggregate dietary/allergy counts. Use approved business contacts only; otherwise mark contacts TBD for the planner to restore before sending.
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
RFP header: Draft — planner review required; Sample Event; issuer/contact: TBD.
Event overview: Example Hall; headcount: 40; date/address/budget: TBD.
Load-in: 2:00 PM; load-out: 9:00 PM; remaining schedule: TBD.
Scope and requirements: dinner catering; 2 guests with peanut allergy.
Submit written allergen-handling/cross-contact procedure, including controls and limitations.
Venue constraints: Vendor must plan around: warming kitchen only; no cooking on site.
Pricing format: separate lines for each service/equipment item, labor, delivery, service charge, tax, gratuity; unsupplied values: Vendor to quote.
Vendor documents required: certificate of insurance; deposit schedule; cancellation/postponement and payment terms; written allergen procedure; experience/references; venue operational plan.
Timeline and evaluation: response deadline, decision date, questions deadline: TBD.
Proposed evaluation criteria — confirm with the client before sending: compliance with stated requirements; completeness and clarity of itemized pricing; relevant experience and references; operational plan for the venue constraints; allergen-handling/safety procedures; insurance and terms.
Open items (TBD): What are the issuer/contact, date/address, budget, remaining schedule, coverage requirements, deadlines, and any further venue constraints?
Will the client confirm or edit the proposed evaluation criteria before sending?
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

RFP HEADER
- Request for proposal: Audio-visual production (staging, projection, audio, confidence monitor, livestream)
- Status: Draft — planner review required
- Issued by: TBD
- Contact: TBD (planner to insert approved business contact before sending)
- Response deadline: February 1, 2027

EVENT OVERVIEW
- Client/event: Sample Foundation (fictional) — annual gala
- Event date(s): Saturday, April 24, 2027
- Venue/address: Example Hotel Grand Ballroom, Austin, TX (fictional); street address: TBD
- Headcount and breakdowns: 350 guests at 35 rounds of 10
- Schedule, including load-in/out:
    Load-in: from 07:00
    Setup complete / rehearsal / sound check: TBD
    Program: 18:30–22:30 — welcome, 3 speakers, a 6-minute video, live auction, band 21:00–22:30 (band brings its own backline)
    Strike start: TBD
    Load-out: complete by 01:00 (date of 01:00 cutoff: TBD — see Open items)
- Budget: TBD

SCOPE AND REQUIREMENTS
- Stage: 24 ft x 12 ft x 2 ft high
- 2 projection screens (size, aspect ratio, placement, projectors, and content sources: TBD)
- 4 wireless handheld mics + 2 lavaliers
- Confidence monitor for speakers
- Livestream of the speeches only (not the auction); platform, viewer count, and switching/graphics requirements: TBD
- Playback of the 6-minute video (file format and source: TBD)
- Program support for welcome, 3 speakers, live auction
- Band 21:00–22:30 brings its own backline; any AV vendor support for the band (PA, mixing, monitors, inputs): TBD
- Vendor to state crew roles, head count, and hours required to deliver the above within the load-in/load-out window

VENUE CONSTRAINTS
- Vendor must plan around: House rigging points available, but the venue requires its in-house rigger for any rigging.
- Vendor must plan around: Load-in from 07:00.
- Vendor must plan around: Load-out complete by 01:00.
- Power, loading dock/freight access, union or in-house AV requirements, internet/bandwidth for livestream, ceiling height, rigging point locations and load limits, in-house rigger scheduling and charges: TBD — planner to confirm with venue.

PRICING FORMAT
(Retain supplied values exactly; otherwise "Vendor to quote." Identify estimates, included charges, and inapplicable charges explicitly. Do not bundle charges.)

Item                                        | Quantity/hours   | Unit rate/charge basis | Amount
Stage 24 ft x 12 ft x 2 ft high             | Vendor to quote  | Vendor to quote        | Vendor to quote
Projection screens                          | 2                | Vendor to quote        | Vendor to quote
Projectors                                  | Vendor to quote  | Vendor to quote        | Vendor to quote
Wireless handheld mics                      | 4                | Vendor to quote        | Vendor to quote
Lavalier mics                               | 2                | Vendor to quote        | Vendor to quote
Confidence monitor                          | Vendor to quote  | Vendor to quote        | Vendor to quote
PA / audio system                           | Vendor to quote  | Vendor to quote        | Vendor to quote
Video playback / switching                  | Vendor to quote  | Vendor to quote        | Vendor to quote
Livestream (speeches only)                  | Vendor to quote  | Vendor to quote        | Vendor to quote
Rigging hardware (in-house rigger per venue)| Vendor to quote  | Vendor to quote        | Vendor to quote
Labor, by role (list each role separately)  | Vendor to quote  | Vendor to quote        | Vendor to quote
Setup                                       | Vendor to quote  | Vendor to quote        | Vendor to quote
Strike                                      | Vendor to quote  | Vendor to quote        | Vendor to quote
Delivery                                    | Vendor to quote  | Vendor to quote        | Vendor to quote
Service charge                              | Vendor to quote  | Vendor to quote        | Vendor to quote
Tax                                         | Vendor to quote  | Vendor to quote        | Vendor to quote
Gratuity                                    | Vendor to quote  | Vendor to quote        | Vendor to quote

Vendor to state whether in-house rigger charges are billed through the vendor or directly by the venue, and to list any equipment or labor it considers inapplicable.

VENDOR DOCUMENTS REQUIRED
- Certificate of insurance; coverage types/limits: TBD
- Deposit schedule; cancellation/postponement terms; payment terms
- Relevant experience and references (gala/ballroom productions with livestream)
- Venue operational plan addressing the in-house rigger requirement, the 07:00 load-in, and the 01:00 load-out cutoff
- Crew list by role and proposed run-of-show technical plan (speeches, video, auction, band changeover, livestream start/stop)
- Permit/license documentation: none identified in the brief — TBD if required

TIMELINE AND EVALUATION
- Questions deadline: TBD
- Response deadline: February 1, 2027
- Decision date: February 12, 2027
- Proposed evaluation criteria — confirm with the client before sending:
    Compliance with stated requirements
    Completeness and clarity of itemized pricing
    Relevant experience and references
    Operational plan for the venue constraints
    Insurance and terms
  (No weights or rankings assigned.)

OPEN ITEMS (TBD)
- Issuer and contact — Which planner/agency and approved business contact should appear on the RFP?
- Venue street address — What is the full address of Example Hotel Grand Ballroom?
- Budget — Is there an AV budget or range to disclose, or is it withheld?
- Load-out date — Does "complete by 01:00" mean 01:00 on Sunday, April 25, 2027? The brief does not state the date.
- Setup/rehearsal/strike times — When must setup be complete, when is sound check/rehearsal, and when may strike begin?
- Screen specs — What size/aspect ratio are the 2 screens, where are they placed, and does the vendor supply projectors?
- Video playback — Does the AV vendor play the 6-minute video? What format and who supplies it?
- Livestream — What platform, expected viewer count, and switching/graphics are required? Does the venue provide internet/bandwidth?
- Band — Does the AV vendor provide PA, mixing, or monitors for the band, or is the band fully self-contained beyond backline?
- Auction — Does the live auction need any AV support (bid displays, auctioneer mic) beyond the listed mics?
- Rigging — Are rigging point locations, load limits, and in-house rigger fees/scheduling known? Who is billed for the rigger?
- Additional venue constraints — Power, loading dock, union labor, in-house AV exclusivity or surcharges, ceiling height?
- Insurance — What coverage types and limits does the client or venue require?
- Questions deadline — By when must vendors submit questions?
- Permits/licenses — Are any required (e.g., livestream music licensing)? None identified in the brief.
- Will the client confirm or edit the proposed evaluation criteria before sending?

Note: planner must replace the proposed criteria label with client-approved criteria and verify all items above with client and venue before release.

