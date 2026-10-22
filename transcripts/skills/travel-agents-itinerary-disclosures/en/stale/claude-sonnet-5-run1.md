# Transcript — skill travel-agents-itinerary-disclosures [en] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:56:25+00:00
- duration_s: 59.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 2ce59da7b61f221b7abd7bc6255179af620cb7d79c338cb021458384e8711987
- skill_sha256: 5b150c8c5aec468562a22966d7c68720b3d2fb3485be4956fdf732f5f054fe78

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: travel-agents-itinerary-disclosures
description: "Use when an advisor pastes traveler profiles, dates, destinations, constraints, and agency terms to draft a day-by-day itinerary with booking disclosures and confirmation tasks."
---

# Itinerary + Booking Disclosures Builder

## What it does

Drafts a client-facing itinerary covering the supplied dates and night split, with transfer days identified. Applies traveler constraints visibly and flags factual travel details for confirmation. Copies agency booking terms verbatim and provides a booking and confirmation checklist. A responsible advisor reviews the draft before sending it; this skill does not book travel.

## Inputs it expects

- De-identified traveler profile: party size, adults, children with ages, and non-identifying labels.
- Arrival and departure dates, including year; destinations in order; nights at each destination.
- Fixed bookings and their status, including any overnight travel or date changes in transit.
- Constraints: mobility, diet/allergies, children's ages, no rental car, pace, and other limits.
- Agency booking terms exactly as written, including deposit, final payment, and insurance acceptance; include other terms if supplied.
- Optional interests, budget, and preferred tone.

Ask once in a consolidated list for missing or conflicting information; never guess.
If exact dates, route order, or night allocation cannot be established, request clarification instead of producing a complete itinerary.
For other missing inputs, proceed only as a provisional draft and list each as MISSING under "To book / to confirm"; do not assume no constraints.

## Procedure

1. Extract dates, route, night split, booking status, every constraint, and the agency's exact terms into a working list.
   Preserve the supplied terms separately so generated notes cannot alter them.
2. Calculate departure date minus arrival date in calendar nights and show the arithmetic.
   Sum destination nights and any explicitly supplied transit nights; show that arithmetic too.
   If totals conflict, or time-zone/date-line travel makes allocation unclear, stop for clarification; do not repair the inputs yourself.
3. Allocate every overnight to its supplied destination or transit segment before adding activities.
   Create one entry per calendar date, arrival through departure inclusive; label each with day number, date, and overnight.
   Mark departure as "no overnight" unless the supplied trip scope explicitly includes one.
4. Label every movement between overnight destinations "TRANSFER DAY" and identify its endpoints.
   Also label arrival and departure transfer days when a transfer is planned; keep activities light.
   Use supplied transport or propose a constraint-compatible mode labeled "proposed — [confirm]"; never imply availability or a booking.
5. Apply each constraint in specific day entries and explain the corresponding adjustment in "Notes on your requests."
   Address mobility, diet/allergies, children's ages, no rental car, and pace whenever supplied.
   Avoid self-drive for no-rental-car requests; use rest blocks for slower pace and age-appropriate proposals for children.
   Treat accessibility and suitability as unverified supplier details, not guarantees.
6. Identify each meal, food activity, hotel meal service, or transport meal affected by a diet or allergy.
   Place "[confirm] — allergy/diet with supplier" beside each affected item and create a corresponding checklist task.
   If meals are not individually planned, put a supplier-confirmation note on every affected day.
   Never claim an allergy can be safely accommodated.
7. Mark every price, opening hour, transport time or duration, age/height limit, and entry rule "[confirm]".
   This applies even when supplied by the user; omit unknown values rather than inventing plausible ones.
   Also flag unverified availability, accessibility, and supplier suitability.
   Traveler ages and trip dates are inputs, not supplier age limits or entry rules.
8. Copy all supplied agency booking terms verbatim into a clearly bounded block under "Booking terms and disclosures."
   Preserve every word, figure, punctuation mark, and line break; do not insert flags into that block.
   If the block contains a fact covered by step 7, immediately follow it with a separate note identifying that item and marking it "[confirm]".
   Outside the block, list each absent deposit, final-payment, or insurance-acceptance provision as "Not provided by agency — advisor to supply."
   Do not draft substitute terms or infer insurance acceptance.
9. After the terms, direct travelers to official government sources for their citizenship, destinations, and transit points to check passport, visa, and entry requirements.
   Direct travelers to their insurer to confirm coverage; state that this draft does not determine entry eligibility or coverage.
   Do not add source names, citations, or URLs when none have been authorized.
10. Build "To book / to confirm" as checkboxes covering all proposed unbooked services, transfers, confirmation flags, supplier allergy checks, and MISSING inputs.
    Include government entry-document checks and insurer coverage checks; distinguish bookings held from services still to book.
11. Audit before output: day entries equal calendar nights plus one; allocated nights match every supplied location total.
    Check every date, transfer label, constraint mapping, confirmation flag, and checklist task.
    Compare the terms block character for character with the input.
    Scan numbers, currency symbols, times, and requirement language for unflagged facts covered by step 7; correct failures before returning the draft.

## Output format

```markdown
## Trip at a glance
- Status: [draft / provisional draft; missing inputs if any]
- Travelers: [de-identified party and supplied ages]
- Dates: [arrival–departure]; nights: [date subtraction]
- Route and nights: [ordered allocation and sum]

## Day by day
- Day [number] — [date] — [plan]; overnight: [place / no overnight].
- [On applicable days: TRANSFER DAY, endpoints, mode and booking status; details [confirm]]
- [Affected day/item: [confirm] — allergy/diet with supplier]
[Repeat for every supplied date; do not omit intermediate days.]

## Notes on your requests
- [Each supplied constraint]: [specific day-level adjustment; uncertainty [confirm]]

## Booking terms and disclosures
Agency terms — verbatim:
[Exact supplied text, with original line breaks]
End of agency terms.
[Separate confirmation notes and missing-term notices, if applicable]
Check passport, visa, and entry requirements with official government sources for your citizenship, destinations, and transit points.
Ask your insurer to confirm coverage; this draft does not determine entry eligibility or coverage.

## To book / to confirm
- [ ] To book: [proposed service and day]
- [ ] To confirm: [flagged detail, supplier allergy/diet check, or missing input]
- [ ] Check government entry-document requirements and insurer coverage.
```

## Hard limits

- Never invent bookings, availability, prices, rules, agency terms, legal requirements, statistics, or citations.
- Never state the facts listed in procedure step 7 as confirmed; preserve [confirm] labels, including separate notes for verbatim terms.
- Never change supplied dates or night splits without authorization, guarantee allergy safety, or determine visa eligibility or insurance coverage.
- The responsible advisor, and a licensed professional where applicable, must verify itinerary feasibility, supplier details, constraint suitability, all flagged items, booking status, and exact authorized agency terms before release.
- Unresolved details must remain visibly flagged; the advisor must decide whether the draft can be sent without misleading the client.
- Seller-of-travel registration and disclosure rules vary by state — the agency confirms its own obligations. UK/AU practitioners must verify their local obligations; this skill does not state those rules.
- No official AI-specific guidance was verified for this profession. Check with your licensing body or regulator. No official citations or URLs are supplied.
- Privacy: de-identify inputs before processing; use non-identifying traveler labels and only agency-approved tools. Exclude passport numbers, full birth dates, payment credentials, contact details, and medical records; retain only necessary ages and functional dietary/mobility constraints.
- Before sending, see references/checklist.md.

## Example

Input (fictional; places and travelers are invented):
> Travelers: Sample party, two adults; July 1–3, 2027.
> Route: Sample Bay 1 night, Example Harbor 1 night; no bookings held.
> Constraints: no rental car, relaxed pace, peanut allergy; meals not individually planned.
> Agency terms: Deposit due at booking. Final payment due before departure. Insurance acceptance must be recorded.

Output (abbreviated):
> ## Trip at a glance
> Sample party, two adults; July 1–3, 2027; 3 − 1 = 2 nights; Sample Bay 1 + Example Harbor 1 = 2.
> ## Day by day
> Day 1 — July 1: settle in and rest; overnight Sample Bay; meals: [confirm] — allergy with supplier.
> Day 2 — July 2 — TRANSFER DAY: Sample Bay → Example Harbor; private transfer proposed — [confirm]; rest; overnight Example Harbor; meals: [confirm] — allergy with supplier.
> Day 3 — July 3: departure; no overnight; meals: [confirm] — allergy with supplier.
> ## Notes on your requests
> No rental car: proposed private transfer; relaxed pace: rest Days 1–2; peanut allergy: supplier checks Days 1–3.
> ## Booking terms and disclosures
> Agency terms — verbatim:
> Deposit due at booking. Final payment due before departure. Insurance acceptance must be recorded.
> End of agency terms. Check official government sources for passport, visa, and entry requirements for your citizenship, destinations, and transit points; ask your insurer about coverage. This draft determines neither eligibility nor coverage.
> ## To book / to confirm
> - [ ] Book both stays and Day 2 transfer; confirm transfer availability, supplier allergy arrangements Days 1–3, government entry-document requirements, and insurer coverage.
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Build the client itinerary with our booking terms.
Travellers: family of four (fictional "the Samples"), kids aged 6 and 9.
Trip: Rome 4 nights, then Florence 3 nights, June 14–21, 2027 (arrive Rome June 14, depart Florence June 21).
One child has a tree-nut allergy and carries an EpiPen. No rental car. Pace: one major sight per day, pool/downtime in the afternoons.
Interests: gelato, the Colosseum, hands-on activities for kids.
Agency booking terms: "Deposit of 20% at booking, non-refundable. Final payment due 60 days before departure. Travel insurance is offered; the client must accept or decline it in writing."
````

## Output (verbatim stdout, session metadata stripped)

TRIP AT A GLANCE
Status: provisional draft — bookings not yet held; several details require confirmation (see checklist)
Travelers: Family of four ("the Samples"), two adults, children aged 6 and 9
Dates: June 14–21, 2027; nights = 21 − 14 = 7
Route and nights: Rome 4 + Florence 3 = 7 (matches total nights)

DAY BY DAY

Day 1 — June 14 — Arrival in Rome. Airport-to-hotel transfer proposed — [confirm] mode, timing, booking. Easy settle-in afternoon; gelato stop nearby (kid-friendly) — [confirm] — allergy/diet with supplier. Overnight: Rome.

Day 2 — June 15 — Rome. Major sight: Colosseum — [confirm] opening hours, ticket prices, and any child age/height entry rules. Afternoon: pool/downtime at hotel. Meals: [confirm] — allergy/diet with supplier. Overnight: Rome.

Day 3 — June 16 — Rome. Major sight/activity: hands-on kids' activity proposed (e.g., mosaic or cooking-for-kids workshop) — [confirm] availability, pricing, and allergy suitability. Afternoon: pool/downtime. Meals: [confirm] — allergy/diet with supplier. Overnight: Rome.

Day 4 — June 17 — Rome. Major sight: free-choice sight proposed — [confirm] selection, hours, pricing. Afternoon: pool/downtime; gelato tasting proposed — [confirm] — allergy/diet with supplier. Overnight: Rome.

Day 5 — June 18 — TRANSFER DAY: Rome → Florence. Mode proposed — high-speed train (no rental car, per request) — [confirm] schedule, fare, booking. Light arrival afternoon in Florence; pool/downtime if available — [confirm]. Meals: [confirm] — allergy/diet with supplier. Overnight: Florence.

Day 6 — June 19 — Florence. Major sight proposed (e.g., Duomo) — [confirm] hours, pricing, suitability for ages 6/9. Afternoon: pool/downtime. Meals: [confirm] — allergy/diet with supplier. Overnight: Florence.

Day 7 — June 20 — Florence. Major sight/activity: hands-on kids' activity proposed (e.g., gelato-making class) — [confirm] availability, pricing, and tree-nut allergy suitability (gelato-making in particular needs explicit confirmation given allergy). Afternoon: pool/downtime. Meals: [confirm] — allergy/diet with supplier. Overnight: Florence.

Day 8 — June 21 — Departure from Florence. No overnight. Hotel-to-airport transfer proposed — [confirm] mode, timing, booking. Any departure-day meal: [confirm] — allergy/diet with supplier if applicable.

NOTES ON YOUR REQUESTS

No rental car: all transfers proposed as train/private transfer, no self-drive at any point — [confirm] availability and booking for each proposed transfer.

Pace (one major sight per day, pool/downtime afternoons): applied Days 2–4 and 6–7, each with a single major activity in the morning/midday and a pool/downtime block in the afternoon; travel and arrival/departure days (1, 5, 8) kept light by design.

Tree-nut allergy, EpiPen carried: every meal, gelato stop, and hands-on food activity across all 8 days is flagged [confirm] — allergy/diet with supplier. Carrying an EpiPen is a medical precaution, not a guarantee that any venue can safely accommodate the allergy — this must be verified directly with each supplier, not assumed from this draft.

Children ages 6 and 9: hands-on activities proposed as age-appropriate, but actual age/height limits for sights (e.g., Colosseum underground/attic tours) and activity providers are unverified — [confirm] each.

Interests (gelato, Colosseum, hands-on kids' activities): incorporated into Days 1, 2, 3, 4, 7 as proposed — all pending availability and supplier confirmation.

BOOKING TERMS AND DISCLOSURES

Agency terms — verbatim:
Deposit of 20% at booking, non-refundable. Final payment due 60 days before departure. Travel insurance is offered; the client must accept or decline it in writing.
End of agency terms.

[confirm] — the 20% deposit figure and the 60-days-before-departure final payment timing are factual terms; advisor to confirm the exact calculated final payment calendar date and the deposit amount in currency with the office before quoting the client.
[confirm] — no written insurance acceptance or decline has been recorded for this family; this must be obtained and documented before the trip proceeds, per the agency's own terms.

Check passport, visa, and entry requirements with official government sources for your citizenship, Italy, and any transit points.
Ask your insurer to confirm coverage; this draft does not determine entry eligibility or coverage.

TO BOOK / TO CONFIRM

To book:
[ ] Rome hotel, 4 nights (Days 1–4)
[ ] Florence hotel, 3 nights (Days 5–7)
[ ] Airport-to-hotel transfer, Rome, Day 1
[ ] Rome → Florence transfer, Day 5
[ ] Hotel-to-airport transfer, Florence, Day 8

To confirm:
[ ] Colosseum tickets, hours, and any age/height entry rules — Day 2
[ ] Hands-on kids' activity Rome — availability, pricing, allergy suitability — Day 3
[ ] Day 4 sight selection, hours, and tickets
[ ] Florence sight Day 6 — hours and tickets
[ ] Hands-on activity Florence (e.g. gelato-making) — allergy suitability in particular — Day 7
[ ] Allergy/diet arrangements with each supplier — every meal and food activity, Days 1–8
[ ] Exact calculated final-payment calendar date and deposit amount in currency, per agency terms
[ ] Written insurance acceptance or decline on file for the family, per agency terms

MISSING inputs (advisor to supply):
[ ] Specific hotel selections/names, Rome and Florence
[ ] Flight details and arrival/departure times
[ ] Any fixed bookings already held (none indicated in the request)

[ ] Check government entry-document requirements and insurer coverage.

This is a draft only — please review all [confirm] items and booking status before sending to the Samples.

