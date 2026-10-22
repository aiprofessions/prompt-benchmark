# Transcript — skill travel-agents-itinerary-disclosures [en] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:52:14+00:00
- duration_s: 46.2
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

  Status: PROVISIONAL DRAFT. Missing inputs are listed under "To book / to confirm."
  Travelers: Family of four ("the Samples"): two adults, children aged 6 and 9.
  Dates: Mon June 14 to Mon June 21, 2027. Nights: 21 - 14 = 7 nights.
  Route and nights: Rome 4 (June 14-17) + Florence 3 (June 18-20) = 7 nights. This matches.
  Bookings held: None stated (MISSING).

DAY BY DAY

  Day 1, Mon June 14: ARRIVAL TRANSFER DAY. Arrival point to Rome hotel.
    Mode: private transfer, proposed [confirm]. Arrival point and time are MISSING.
    Plan: Check in. Pool or downtime if the hotel has a pool [confirm]. Short early-evening gelato stroll near the hotel.
    Overnight: Rome.
    Meals and gelato: [confirm] allergy/diet with supplier.

  Day 2, Tue June 15: Major sight: Colosseum.
    Plan: Morning family-oriented guided visit, proposed [confirm]. Tour availability, timed entry, price and age suitability [confirm].
    Afternoon: Pool or downtime.
    Overnight: Rome.
    Meals and gelato: [confirm] allergy/diet with supplier.

  Day 3, Wed June 16: Major sight: hands-on morning for the kids.
    Plan: Option A is a children's museum. Option B is a family pizza-making class, proposed [confirm]. Ingredients, shared surfaces and cross-contact must be checked: [confirm] allergy/diet with supplier.
    Afternoon: Pool or downtime.
    Overnight: Rome.
    Meals: [confirm] allergy/diet with supplier.

  Day 4, Thu June 17: Major sight: easy historic-centre walk (Pantheon area and Trevi Fountain), proposed.
    Plan: Morning walk. Short distances and stroller or break needs [confirm]; mobility needs are MISSING.
    Afternoon: Pool or downtime. Pack for tomorrow's transfer.
    Overnight: Rome.
    Meals and gelato: [confirm] allergy/diet with supplier.

  Day 5, Fri June 18: TRANSFER DAY. Rome to Florence.
    Mode: Train, proposed [confirm]. Times, duration, fares and seat availability [confirm]. Hotel-to-station transfers at each end, proposed [confirm].
    Plan: No major sight. Check in, then pool or downtime.
    Overnight: Florence.
    Meals, including any onboard food: [confirm] allergy/diet with supplier.

  Day 6, Sat June 19: Major sight: family museum visit (e.g. a kid-oriented Uffizi or Palazzo Vecchio tour), proposed [confirm].
    Plan: Availability, entry rules, timed tickets, price and age suitability [confirm].
    Afternoon: Pool or downtime.
    Overnight: Florence.
    Meals and gelato: [confirm] allergy/diet with supplier.

  Day 7, Sun June 20: Major sight: hands-on morning, proposed (e.g. an interactive Leonardo-style museum or Boboli Gardens).
    Plan: Opening hours, Sunday operation, price and suitability [confirm].
    Afternoon: Pool or downtime. Farewell gelato.
    Overnight: Florence.
    Meals and gelato: [confirm] allergy/diet with supplier.

  Day 8, Mon June 21: DEPARTURE TRANSFER DAY. Florence hotel to departure point.
    Mode: Private transfer, proposed [confirm]. Departure point and time are MISSING.
    Overnight: None.
    Meals: [confirm] allergy/diet with supplier.

NOTES ON YOUR REQUESTS

  Tree-nut allergy (EpiPen carried):
    Every day's meals carry a supplier check. This applies to hotel breakfasts, restaurants, the train and the Day 3 class.
    Gelato is a particular concern because pistachio, hazelnut and almond flavours are common and scoops or counters may be shared. Each shop must be asked directly about cross-contact.
    This draft cannot confirm that any supplier can safely accommodate the allergy. The family should follow their own allergy action plan throughout.

  No rental car:
    All movement uses private transfers, train or walking. Every mode is proposed only and must be confirmed.

  Pace:
    One major sight is planned each morning.
    Afternoons are kept for pool or downtime. Hotel pools are unverified [confirm].
    Transfer days (Days 1, 5 and 8) have no major sight.

  Children aged 6 and 9:
    Tours and activities are family-oriented proposals.
    Age suitability, age or height limits and child pricing all need confirming [confirm].

  Interests:
    Colosseum: Day 2.
    Hands-on activities: Days 3 and 7.
    Gelato: Days 1, 2, 4, 6 and 7, with an allergy check each time.

  Mobility, budget and other dietary needs:
    Not provided (MISSING). No assumption has been made that there are no constraints.

BOOKING TERMS AND DISCLOSURES

  Agency terms, verbatim:
  Deposit of 20% at booking, non-refundable. Final payment due 60 days before departure. Travel insurance is offered; the client must accept or decline it in writing.
  End of agency terms.

  Confirmation notes:
    The 20% deposit figure and the 60-day final payment deadline need confirming [confirm].
    The agency should also specify which date counts as "departure" (June 14 or June 21), so the exact final-payment date can be stated to the client.

  Entry requirements:
    Check passport, visa and entry requirements with official government sources for your citizenship, destinations and transit points.

  Insurance:
    Ask your insurer to confirm coverage, including coverage related to the child's allergy.
    This draft does not determine entry eligibility or coverage.

TO BOOK / TO CONFIRM

  Bookings held: none stated (MISSING). Confirm whether any flights or hotels are already held.

  To book:
  [ ] Rome hotel, 4 nights (June 14-17). Confirm pool, family room and breakfast allergy handling.
  [ ] Florence hotel, 3 nights (June 18-20). Confirm pool, family room and breakfast allergy handling.
  [ ] Day 1: arrival private transfer.
  [ ] Day 2: Colosseum family tour or timed entry.
  [ ] Day 3: children's museum or pizza-making class.
  [ ] Day 5: Rome to Florence train, plus station transfers at both ends.
  [ ] Day 6: Florence family museum tour.
  [ ] Day 7: interactive museum or gardens.
  [ ] Day 8: departure private transfer.

  To confirm:
  [ ] All flagged prices, opening hours, transport times and durations, age or height limits, and entry rules.
  [ ] Availability, accessibility and suitability for children aged 6 and 9.
  [ ] Tree-nut allergy and cross-contact handling with every supplier for Days 1-8: hotels, restaurants, gelato shops, the train and the Day 3 class.
  [ ] Deposit percentage, the final-payment deadline and the definition of "departure" with the agency.
  [ ] Written insurance acceptance or decline from the client.
  [ ] Government entry-document requirements for each traveler's citizenship and any transit points.
  [ ] Insurer coverage, including allergy-related medical coverage.

  Missing inputs:
  [ ] Arrival point and time (Day 1).
  [ ] Departure point and time (Day 8).
  [ ] Any existing bookings.
  [ ] Mobility needs (e.g. stroller, walking limits).
  [ ] Budget.
  [ ] Any other dietary needs.
  [ ] Preferred tone.

Advisor review is required before sending. Verify feasibility, all flagged items and the exact authorized agency terms. Seller-of-travel disclosure obligations vary by jurisdiction, and the agency should confirm its own.

