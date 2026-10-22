# Transcript — skill interior-designers-ffe-schedule [en] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:29:24+00:00
- duration_s: 79.8
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: eeadbfa66d32969297c2242b448d978eea04d8fcf0349b03628c502f7e5d29fd
- skill_sha256: 6eb137f312fead5efe9e1d179ed3df666d61ac861c05f00a59276b0e6caf2c34

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Use when a designer pastes a room brief and asks for an FF&E schedule draft with sizing calculations, budget allowances, reuse status, and lead-time checks."
---
# Client Brief to FF&E Schedule Draft

## What it does
Turns a single-room client brief into a draft furniture, fixtures, and equipment (FF&E) schedule for professional review. Includes every requested item and retained piece, sizing calculations where supported, proportional budget allowances, and order-by calculations where quoted lead times permit. It does not select products, establish prices, or confirm compliance.

## Inputs it expects
- Room use, dimensions, units, ceiling height, and known doors, windows, or other constraints.
- Requested items and quantities.
- Users, relevant accessibility needs, children, and pets; omit identifying details.
- Likes and dislikes, including materials, colors, finishes, and styles.
- Total budget, currency, and scope: purchases, tax, freight, installation, fees, and contingency.
- Install date and quoted lead times, including calendar/business-day basis and what starts the lead time.
- Existing pieces to keep, quantities, dimensions, condition, and work needed.
- Project type and jurisdiction; a full street address is not needed.
- Optional: tag convention, rug border, clearances, budget allocations or weights, and planning buffer.

Ask once in a consolidated list for missing or conflicting inputs. If instructed to proceed, mark gaps "MISSING — confirm" and list them under Questions for the client; never guess source facts. Missing budget or scheduling inputs prevent completion of those checks, not preparation of the rest of the draft.

## Procedure
1. Extract the brief's figures and constraints without changing them.
   - Copy quantities, dimensions, total budget, currency, dates, lead times, and units exactly.
   - Show conversions separately; flag ambiguous dates, units, or conflicting figures.
2. Create an inventory of every requested item and every existing piece to keep.
   - Give each entry a unique tag using the supplied convention or sequential tags.
   - If a retained piece explicitly fulfills a request, use one row and identify both roles.
   - Otherwise retain both entries and ask whether reuse replaces the requested purchase.
3. Create a schedule row for each inventory entry.
   - Enter tag, item, quantity, target size, material/performance notes, allowance, lead-time check, and status.
   - Use status "new" or "existing-reuse"; if unresolved, write "MISSING — confirm status."
   - Mark retained pieces "existing-reuse"; flag missing quantities or measurements rather than assuming them.
4. Apply likes and dislikes before writing material notes.
   - State "Excluded per client: …" under Design intent and repeat exclusions in affected rows.
   - Do not propose disliked materials, finishes, or styles.
   - For conflicting requests, retain a neutral row with "HOLD — client conflict" and ask for resolution.
5. Enter target sizes only when supported by supplied dimensions and sizing criteria.
   - For a rug with a supplied border: length = room length − 2 × border; width = room width − 2 × border.
   - Show substitutions, results, and units in the target-size cell.
   - For other derived sizes, show the supplied constraints and arithmetic.
   - Without necessary measurements or criteria, write "MISSING — designer to size."
   - Flag nonpositive results and known circulation/opening conflicts; never call a target size a confirmed fit.
6. Translate users and pets into relevant row-specific requirements to verify.
   - For children, consider rounded/eased edges and stability; state these as requirements to verify.
   - For pets or frequent spills, require suitable cleanability and durability; request manufacturer evidence.
   - Never imply an unspecified product has a property or satisfies an accessibility requirement.
7. Fill every allowance cell using a disclosed proportional allocation of the client's stated total.
   - Restate total, currency, and scope exactly; label every amount "allowance — estimate, confirm with quotes."
   - Honor client-supplied allocations or weights. Flag allocations that exceed the total or conflict.
   - Record fixed allocations and explicit reserves separately; subtract them from the total before splitting the balance.
   - For unallocated item rows, use supplied weights; otherwise propose equal weight per row, clearly labeled provisional.
   - Compute allowance = remaining balance × row weight ÷ sum of remaining weights; show arithmetic and each allocation as a percentage of the original total.
   - Include reuse rows: their provisional allowance covers possible handling/work, not a product price; ask for confirmation.
   - Use zero only for a client-confirmed no-cost row; label it with the same allowance wording and show 0%.
   - Round consistently to currency precision; assign any rounding remainder to the largest eligible allocation and disclose it.
   - Reconcile item allowances plus separately labeled reserves to the client's total without double counting.
   - Never leave cells blank or write "none." If total, currency, or allocation conflicts prevent calculation, write "allowance — estimate, confirm with quotes; MISSING — [input]" and ask.
   - List uncertain coverage of tax, freight, installation, fees, and contingency; a reconciled split does not prove affordability.
8. Calculate a concrete order-by date from the install date and the longest quoted lead time.
   - Inventory quoted durations by tag, including work on reuse pieces; flag every unquoted item.
   - Confirm duration basis and start/end conditions; do not assume production time includes transit or installation.
   - For calendar weeks, show weeks × 7 = calendar days. For business days, require the applicable working-day/holiday calendar.
   - Identify the longest comparable quoted duration and its tag; show order-by = install date − longest quoted duration = [YYYY-MM-DD].
   - Put that shared deadline in each applicable row, alongside its own quoted duration or missing-data flag.
   - If any duration is missing or excludes necessary stages, label the date provisional and name the unresolved dependencies.
   - If a buffer is supplied, also calculate install date − longest duration − buffer = recommended order date.
   - If the verified current date is later than the deadline, flag "AT RISK — calculated order-by date has passed; confirm feasibility."
   - If the install date, lead times, basis, or calendar is insufficient, show the formula and "MISSING — order-by date pending"; ask rather than invent a date.
9. Build a tag-specific Specs to verify list.
   - Address flammability, abrasion/double rubs, cleaning codes, and slip resistance for each relevant material/use.
   - Request manufacturer data and test-method context; never present a rating or compliance conclusion as verified fact.
   - For apparently inapplicable categories, state the reason for professional review; do not silently omit them.
10. Produce the six sections below in order.
    - List all missing inputs and conflicts under Questions for the client.
    - Separate client decisions from manufacturer/vendor checks and responsible-professional verification.
11. Reconcile before returning the draft.
    - Check every request and retained piece against the inventory; check quantities, statuses, exclusions, and sizing arithmetic.
    - Check allowance labels, proportional calculations, reserve treatment, and total reconciliation.
    - Check date subtraction, duration basis, missing quotes, and provisional warnings.
    - Remove invented product identities, prices, ratings, compliance claims, and citations.

## Output format
```markdown
## Design intent
[Use, users/pets, likes, requirements. Excluded per client: …; unresolved conflicts: …]
## FF&E schedule
| Tag | Item | Qty | Target size (calculation if derived) | Material / performance notes (verify) | Budget allowance | Lead-time check / order-by | Status |
|---|---|---|---|---|---|---|---|
| [tag] | [item] | [qty or MISSING] | [size/calculation or MISSING] | [requirements/exclusions] | [amount; allowance — estimate, confirm with quotes; %] | [quoted duration; date/calculation reference or MISSING] | [new / existing-reuse / MISSING] |
## Budget check
Client total: [exact amount/currency]. Scope: [supplied scope and gaps].
[Fixed allocations/reserves; balance; weights; line calculations; percentages; rounding.]
[Item allowances + reserves = total, or unresolved calculation blockers.]
[All allocations are allowances — estimates, confirm with quotes; uncertain cost coverage.]
## Lead-time check
[Quoted durations by tag, basis, conditions, and missing quotes.]
Longest quoted: [tag/duration]. Order-by = [install] − [duration] = [date, or MISSING].
[Buffer calculation, dependencies, provisional warning, and risk flag where applicable.]
## Specs to verify
[By tag: manufacturer evidence for all four categories; nonapplicability reasons for review.]
## Questions for the client
[Client decisions/missing inputs; separately identify vendor and professional checks.]
```

## Hard limits
- Never invent products, names, model numbers, prices, availability, lead times, ratings, statistics, or compliance claims.
- Do not add legal citations, article numbers, named regulators, URLs, or unsupported dates. Supplied project dates and explicitly calculated scheduling dates are permitted.
- No official AI-specific guidance was verified for this profession; check with your licensing body or regulator. No official sources are supplied for citation.
- Fire/flammability codes for furnishings depend on project type and jurisdiction; the designer confirms them.
- A licensed professional where required, or the responsible professional, must verify measurements, fit, circulation, applicable accessibility requirements, manufacturer evidence, budget scope, quotes, and procurement timing.
- UK/AU practitioners must verify local requirements; do not assume US requirements apply.
- Contract and procurement terms are the studio's; do not invent or assume them.
- Never silently omit requests, specify disliked features, or present an incomplete budget/date check as complete.
- Privacy: de-identify briefs, removing names, addresses, access codes, and identifying image metadata; use only studio-approved tools and the minimum necessary information.
- Before issue or procurement, see references/checklist.md.

## Example
Input (fictional):
```text
Sample Room: 12 × 16 ft; requests 1 rug with a 2 ft border on every side.
Keep 1 wood side table, 20 × 20 × 22 in; refinishing quote: 3 calendar weeks to completion.
One dog; likes blue; dislikes velvet. USD 1,200 all-in; allocation weights rug 3, table 1.
Install 2027-03-15; rug quote: 8 calendar weeks from order to delivery. Proceed with gaps flagged.
```
Output (abbreviated):
```markdown
## Design intent
Blue; dog-related cleanability to verify. Excluded per client: velvet.
## FF&E schedule
| Tag | Item | Qty | Target size | Notes (verify) | Budget allowance | Lead-time check / order-by | Status |
|---|---|---|---|---|---|---|---|
| 01 | Rug | 1 | 12−2×2 = 8 ft; 16−2×2 = 12 ft | No velvet; cleanability and slip resistance required | USD 900; allowance — estimate, confirm with quotes; 75% | 8 calendar weeks; provisional 2027-01-18 | new |
| 02 | Wood side table | 1 | 20 × 20 × 22 in supplied | Refinish; cleanable finish required | USD 300; allowance — estimate, confirm with quotes; 25% | 3 calendar weeks; provisional 2027-01-18 | existing-reuse |
## Budget check
USD 1,200 all-in: 1,200×3/4 = 900; 1,200×1/4 = 300; sum = 1,200. Tax/freight/install coverage unconfirmed.
## Lead-time check
01 longest: 8×7 = 56 days; 02: 3×7 = 21 days. Order-by = 2027-03-15 − 56 days = 2027-01-18; provisional pending installation needs and refinishing start conditions.
## Specs to verify
01: manufacturer flammability, abrasion/test method, cleaning guidance/code, slip data. 02: finish cleaning data; furnishing flammability applicability for designer review; upholstery double rubs/cleaning codes and walking-surface slip data appear inapplicable to wood table.
## Questions for the client
Client: project type/jurisdiction, cost coverage, installation needs/buffer? Vendor: refinishing start conditions? Professional: fit, data applicability, and fire requirements?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Draft the FF&E schedule for this room.
Client: the Example family (fictional). Room: family room 16 ft x 20 ft, 9 ft ceiling, one 8 ft wide window (north wall).
Items wanted: sectional sofa seating 6; area rug leaving an 18 in floor border on every side; coffee table; 2 lounge chairs; 2 floor lamps; drapery for the window.
Existing: walnut media console for the existing 75 in TV — keep it.
Users: two kids (4 and 7) and a large dog that sheds.
Likes: warm wood, oatmeal tones. Dislikes: glass tabletops, velvet.
Budget: $28,000 total FF&E including tax and delivery. Install date: March 15, 2027. Upholstery lead time quoted by our vendors: 14–16 weeks.
````

## Output (verbatim stdout, session metadata stripped)

Draft prepared with gaps flagged (no instruction to pause, so missing inputs are marked and collected in Questions). Figures are copied exactly; conversions shown separately.

DESIGN INTENT
  Use: family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft wide window on north wall. Doors/other openings not supplied.
  Users: two children (4 and 7) and one large shedding dog. Requirements to verify: rounded/eased edges and stability on tables and lamps; anti-tip provision for console and TV; pet-grade cleanability and abrasion durability on all upholstery, rug, and drapery, with manufacturer evidence.
  Likes: warm wood, oatmeal tones.
  Excluded per client: glass tabletops; velvet.
  Unresolved conflicts: none identified in the brief.
  Project type and jurisdiction: MISSING — confirm (fire/flammability requirements depend on these).

FF&E SCHEDULE
  Columns: Tag | Item | Qty | Target size | Material/performance notes (verify) | Budget allowance | Lead-time check / order-by | Status

  01 | Sectional sofa, seating 6 | 1
     Size: MISSING — designer to size (no sizing criteria, door/opening locations, or layout supplied; room 16 x 20 ft, 9 ft ceiling noted)
     Notes: no velvet; oatmeal tone; pet cleanability, abrasion, and cleaning code per manufacturer; stable base, eased edges for children
     Allowance: $4,000; allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: 14–16 weeks quoted (basis and start condition unconfirmed); order-by 2026-11-23 (provisional)
     Status: new

  02 | Area rug | 1
     Size: border 18 in = 1.5 ft. Length = 20 − 2 x 1.5 = 17 ft; width = 16 − 2 x 1.5 = 13 ft → 13 x 17 ft target. Not a confirmed fit; check against doors/openings not supplied
     Notes: oatmeal tone; pet-shedding cleanability, abrasion, and slip resistance/pad per manufacturer; no velvet pile
     Allowance: $4,000; allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: no quote supplied — MISSING; shared order-by 2026-11-23 (provisional)
     Status: new

  03 | Coffee table | 1
     Size: MISSING — designer to size (depends on 01 dimensions and clearances not supplied)
     Notes: Excluded per client: glass tabletop. Warm wood preferred; rounded/eased edges and stability for children; cleanable finish for pet/spills
     Allowance: $4,000; allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: no quote supplied — MISSING; shared order-by 2026-11-23 (provisional)
     Status: new

  04 | Lounge chairs | 2
     Size: MISSING — designer to size
     Notes: no velvet; oatmeal tone or warm wood frame; pet cleanability, abrasion, cleaning code per manufacturer; stable base
     Allowance: $4,000 (for the pair); allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: 14–16 weeks quoted if upholstered (confirm these are covered by the upholstery quote); order-by 2026-11-23 (provisional)
     Status: new

  05 | Floor lamps | 2
     Size: MISSING — designer to size (9 ft ceiling supplied; no seating heights)
     Notes: weighted/stable base, tip-over resistance, cord management for children and dog; warm wood or oatmeal shade preferred
     Allowance: $4,000 (for the pair); allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: no quote supplied — MISSING; shared order-by 2026-11-23 (provisional)
     Status: new

  06 | Drapery, north window | 1 window (panel count MISSING)
     Size: window width 8 ft supplied; window height, sill/head height, mounting height, and stack-back criteria MISSING — designer to size
     Notes: no velvet; oatmeal tone; cleanability for pet hair; cord/child-safety requirement to verify; flammability per project type
     Allowance: $4,000; allowance — estimate, confirm with quotes; 14.29% (provisional equal weight)
     Lead time: no quote supplied — MISSING (confirm whether the 14–16 week upholstery quote applies to drapery workroom); shared order-by 2026-11-23 (provisional)
     Status: new

  07 | Walnut media console (supports existing 75 in TV) | 1
     Size: console dimensions MISSING — confirm; TV 75 in supplied (diagonal assumed — confirm)
     Notes: condition and work needed MISSING — confirm (none stated); anti-tip/TV anchoring requirement to verify for children; walnut aligns with warm-wood preference
     Allowance: $4,000; allowance — estimate, confirm with quotes; 14.29% (provisional, covers possible handling/work, not a product price; set to 0% only if client confirms no cost)
     Lead time: no work quoted — MISSING; shared order-by 2026-11-23 (provisional)
     Status: existing-reuse

BUDGET CHECK
  Client total: $28,000 total FF&E including tax and delivery. Currency: "$" only — confirm USD.
  Scope supplied: purchases, tax, delivery. Not stated: installation, design/procurement fees, contingency, drapery fabrication/installation, console work.
  Fixed allocations/reserves: none supplied. Balance to split: $28,000.
  Weights: none supplied; provisional equal weight 1 per row, 7 rows, sum 7.
  Line calculation: 28,000 x 1 / 7 = 4,000.00 per row (01–07). Percentage: 1/7 = 14.2857% ≈ 14.29% each; 7 x 4,000 = 28,000. No rounding remainder.
  Reconciliation: 7 x $4,000 = $28,000 = client total. All amounts are allowances — estimates, confirm with quotes. A reconciled split does not prove affordability; equal weighting is a placeholder (e.g., 01 and 04 likely carry more cost than 05 or 07).

LEAD-TIME CHECK
  Quoted: 14–16 weeks for upholstery (vendor quote). Basis (calendar vs business weeks), start condition (order/deposit/COM receipt), and end condition (ship vs deliver vs install) unconfirmed. Applies to 01 and presumably 04; application to 06 unconfirmed.
  Unquoted: 02, 03, 05, 06 (workroom), 07 (any work), plus delivery/installation time if excluded from the quote.
  Longest quoted: 16 weeks (01/04). Assuming calendar weeks: 16 x 7 = 112 calendar days.
  Order-by = 2027-03-15 − 112 days = 2026-11-23 (provisional). (14-week case: 98 days → 2026-12-07, not governing.)
  Buffer: none supplied; recommended order date pending.
  Status vs today (2026-10-20): deadline not passed; 34 days remain. Date is provisional pending basis confirmation, unquoted items, and whether transit/installation are excluded.

SPECS TO VERIFY (manufacturer data and test method required for each; no ratings assumed)
  01, 04: upholstery flammability for project type/jurisdiction; abrasion (double rubs with test method); cleaning code and pet-hair/spill guidance; slip resistance not applicable to seating — designer to confirm.
  02: rug/pad flammability; abrasion/wear data; cleaning guidance; slip resistance of rug-pad system on the floor finish (floor finish MISSING).
  03: finish cleanability/stain data; edge radius and stability; furnishing flammability applicability for designer review; double rubs and walking-surface slip data appear inapplicable to a wood table — designer to confirm.
  05: electrical listing for jurisdiction; base stability/tip test data; shade material flammability and cleanability; abrasion and slip data appear inapplicable — designer to confirm.
  06: textile flammability for project type; cleaning code; abrasion applicability for drapery weight (likely not governing — designer to confirm); cord/child-safety evidence; slip data inapplicable.
  07: existing finish cleanability and any refinish product data; anti-tip/anchoring hardware evidence for console and TV; flammability of any new finish for review; double rubs and slip data appear inapplicable.

QUESTIONS FOR THE CLIENT
  Client decisions / missing inputs:
    1. Currency is USD? Does $28,000 also cover installation, fees, contingency, drapery fabrication, and any console work?
    2. Any preferred budget weights per item, or accept equal provisional split as a starting point?
    3. Project type (private residence?) and jurisdiction (state/country) for fire and accessibility requirements.
    4. Door/opening locations, floor finish, and any required clearances or layout preferences.
    5. Window height, sill/head heights, and preferred drapery mounting (ceiling vs above frame); panel count and operability.
    6. Media console dimensions, condition, and any work needed (refinish, repair, none). Is the TV in scope for mounting/anchoring work?
    7. Any accessibility needs for household members or guests? Any planning buffer before install?
  Vendor checks:
    8. 14–16 weeks: calendar or business weeks? What starts the clock, and does it include transit and delivery? Does it cover 04 and 06?
    9. Lead-time quotes for 02, 03, 05, 06, and any 07 work.
  Responsible professional verification:
    10. Rug size fit against circulation and openings; all target sizes; manufacturer evidence listed above; applicable flammability/accessibility requirements; quotes against allowances; procurement timing before issue (see references/checklist.md).

