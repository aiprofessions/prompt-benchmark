# Transcript — skill travel-agents-itinerary-disclosures [en] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:01:11+00:00
- duration_s: 63.6
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

- Status: Provisional draft. Missing inputs are listed below and as MISSING under "To book / to confirm."
  - Booking status of flights, hotels and transfers was not stated, so this draft assumes nothing is held.
  - Arrival and departure points and times were not supplied.
  - Mobility needs were not stated. This draft does not assume there are none.
  - Dietary needs beyond the tree-nut allergy were not stated.
  - Budget and tone were not supplied.
- Travelers: The Samples, a family of four: two adults (assumed; please confirm) and two children aged 6 and 9. One child has a tree-nut allergy and carries an EpiPen.
- Dates: June 14–21, 2027. Nights: June 21 − June 14 = 7 nights.
- Route and nights: Rome 4 + Florence 3 = 7 nights. This matches the dates, giving 8 day entries.

DAY BY DAY

Day 1 — Mon June 14, 2027 — Arrive Rome. Overnight: Rome.
- TRANSFER DAY (arrival): arrival point → Rome hotel.
  - Private transfer proposed — [confirm]. Arrival point and time are MISSING.
- Plan: settle in, then pool or downtime at the hotel. Pool availability is [confirm]; if there is none, rest in a nearby park.
- Evening: short neighborhood walk and first gelato stop.
- Gelato: [confirm] — allergy/diet with supplier. Ask about tree-nut flavors and shared scoops or cases at each shop.
- Dinner: [confirm] — allergy/diet with supplier.

Day 2 — Tue June 15 — Colosseum. Overnight: Rome.
- Morning (major sight): Colosseum and Roman Forum.
  - Family-oriented guided tour proposed — [confirm].
  - Timed entry, ticket prices and age-based ticket rules: [confirm].
- Afternoon: pool or downtime at the hotel.
- All meals and the gelato stop: [confirm] — allergy/diet with supplier.

Day 3 — Wed June 16 — Hands-on day. Overnight: Rome.
- Morning (major activity): children's "gladiator school"-style experience proposed — [confirm].
  - Supplier, age suitability, price and times: [confirm].
- Alternative: family pasta- or pizza-making class proposed — [confirm] — allergy/diet with supplier. Ask about ingredients and cross-contact.
- Afternoon: pool or downtime.
- All meals and any class food: [confirm] — allergy/diet with supplier.

Day 4 — Thu June 17 — Historic center. Overnight: Rome.
- Morning (major sight): Pantheon and Piazza Navona on foot, with a Trevi Fountain stop.
  - Pantheon entry rules and prices: [confirm].
- Alternative: Vatican Museums with a family tour proposed — [confirm]. Opening days and hours: [confirm].
- Afternoon: pool or downtime, and packing for tomorrow.
- All meals and gelato: [confirm] — allergy/diet with supplier.

Day 5 — Fri June 18 — TRANSFER DAY: Rome → Florence. Overnight: Florence.
- Hotel → Rome station: taxi or private transfer proposed — [confirm].
- Rome → Florence: train proposed — [confirm]. Not booked. Times and duration are [confirm].
- Florence station → hotel: taxi or private transfer proposed — [confirm].
- Afternoon: check in, then pool or downtime. No sightseeing.
- Train snacks and meals: [confirm] — allergy/diet with supplier. Packing your own nut-free snacks is suggested.
- Dinner: [confirm] — allergy/diet with supplier.

Day 6 — Sat June 19 — Uffizi. Overnight: Florence.
- Morning (major sight): Uffizi Gallery.
  - Family-oriented tour or kids' activity format proposed — [confirm].
  - Timed entry, prices and opening hours: [confirm].
- Afternoon: pool or downtime. Boboli Gardens is an optional outdoor alternative; entry and hours [confirm].
- All meals and gelato: [confirm] — allergy/diet with supplier. Florentine almond biscuits (cantucci) and nut-based desserts are common, so ask every time.

Day 7 — Sun June 20 — Hands-on day. Overnight: Florence.
- Morning (major activity): family mosaic or fresco workshop proposed — [confirm]. Age suitability, times and price: [confirm].
- Alternative: interactive Leonardo-themed museum proposed — [confirm]. Sunday opening: [confirm].
- Optional gelato-making class, proposed only if the supplier confirms in writing how it handles tree nuts: [confirm] — allergy/diet with supplier.
- Afternoon: pool or downtime.
- Farewell dinner: [confirm] — allergy/diet with supplier.

Day 8 — Mon June 21 — Depart Florence. No overnight.
- TRANSFER DAY (departure): Florence hotel → departure point.
  - Private transfer proposed — [confirm]. Departure point and time are MISSING.
- Plan: breakfast and checkout only.
- Breakfast and any travel-day food: [confirm] — allergy/diet with supplier.

NOTES ON YOUR REQUESTS

- Tree-nut allergy and EpiPen
  - Every meal, gelato stop, food class and train snack on Days 1–8 is marked for supplier confirmation.
  - Gelato is a known cross-contact risk because of nut flavors and shared scoops or cases. Each shop must be asked directly.
  - This draft cannot confirm that any supplier can safely accommodate the allergy.
  - Carrying the EpiPen through airports and on flights: confirm with the airline [confirm]. Check entry rules for medication with official government sources.
- No rental car
  - All movements are proposed as private transfer, taxi or train. There is no self-drive on any day.
  - Every transfer is unbooked and [confirm].
- Pace (one major sight per day, pool or downtime afternoons)
  - Each day has one morning anchor and a free afternoon.
  - Transfer days (1, 5 and 8) have no sightseeing.
  - Hotel pools are not verified [confirm]. Many central hotels may not have one, so choose hotels with that in mind.
- Children aged 6 and 9
  - Proposed tours and workshops are family-format. Age suitability, age limits and child pricing are all [confirm].
- Interests
  - Colosseum: Day 2.
  - Hands-on activities: Days 3 and 7.
  - Gelato: daily, always subject to the allergy check above.
- Mobility
  - MISSING. Walking-heavy days (2, 4 and 6) need confirmation that they suit everyone in the party.

BOOKING TERMS AND DISCLOSURES

Agency terms — verbatim:
Deposit of 20% at booking, non-refundable. Final payment due 60 days before departure. Travel insurance is offered; the client must accept or decline it in writing.
End of agency terms.

Confirmation notes on the terms:
- "20%" deposit percentage and amount: [confirm].
- "60 days before departure": [confirm] the reference date and the resulting due date.

Check passport, visa, and entry requirements with official government sources for your citizenship, destinations, and transit points.
Ask your insurer to confirm coverage; this draft does not determine entry eligibility or coverage.

TO BOOK / TO CONFIRM

MISSING inputs:
- [ ] MISSING: current booking status of flights, hotels and transfers.
- [ ] MISSING: arrival point and time (Day 1) and departure point and time (Day 8).
- [ ] MISSING: mobility needs for the party.
- [ ] MISSING: dietary needs beyond the tree-nut allergy, and confirmation that there are two adults.
- [ ] MISSING: budget and preferred tone.

To book:
- [ ] Rome hotel, 4 nights (June 14–18). Pool availability [confirm].
- [ ] Florence hotel, 3 nights (June 18–21). Pool availability [confirm].
- [ ] Day 1: arrival transfer.
- [ ] Day 2: Colosseum and Forum family tour or timed tickets.
- [ ] Day 3: gladiator-style experience or cooking class.
- [ ] Day 4: optional Vatican Museums family tour.
- [ ] Day 5: hotel → station transfer, Rome → Florence train, station → hotel transfer.
- [ ] Day 6: Uffizi family tour or timed tickets.
- [ ] Day 7: mosaic or fresco workshop, Leonardo-themed museum, or gelato class.
- [ ] Day 8: departure transfer.

To confirm (supplier details):
- [ ] All prices, opening days and hours, transport times and durations, age limits and entry rules flagged above.
- [ ] Accessibility and age suitability of each tour, workshop and transfer.

To confirm (allergy):
- [ ] Tree-nut allergy and cross-contact handling with both hotels (meal service), every restaurant, every gelato shop, all food classes, and any train catering (Days 1–8).
- [ ] EpiPen carriage policy with the airline. Medication entry rules via official government sources.

To confirm (terms):
- [ ] The deposit percentage and amount, and the final-payment reference date and due date.
- [ ] The client's written acceptance or decline of travel insurance.

Entry and insurance:
- [ ] Check government entry-document requirements and insurer coverage.

Before release, the advisor must verify feasibility, supplier details, constraint suitability, booking status and every flagged item. Also see references/checklist.md.

