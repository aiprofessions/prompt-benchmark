# Transcript — skill interior-designers-ffe-schedule [en] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:53:07+00:00
- duration_s: 66.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: eeadbfa66d32969297c2242b448d978eea04d8fcf0349b03628c502f7e5d29fd
- skill_sha256: 03879137d6a927c65f631b69d2754fbb9b269428ed7ff81551a42e4242125a26

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Use when a designer pastes a room client brief to draft an FF&E schedule with sizes, estimated allowances, reuse status, lead-time checks, and verification questions."
---
# Client Brief to FF&E Schedule Draft

## What it does
Turns a single-room client brief into a draft furniture, fixtures, and equipment (FF&E) schedule for professional review. Includes every requested item and existing piece to keep, with sizing logic, estimated allowances, timing checks, and verification requirements. It does not select products, establish prices, or confirm compliance.

## Inputs it expects
- Room use, dimensions, units, ceiling height, and known doors, windows, or other constraints.
- Requested items and quantities.
- Users, relevant accessibility needs, children, and pets; omit identifying details.
- Likes and dislikes, including materials, colors, finishes, and styles.
- Total budget, currency, and scope: purchases, tax, freight, installation, fees, and contingency.
- Install date and scheduling reference date.
- Existing pieces to keep, their quantities and dimensions, and any work needed.
- Project type and jurisdiction; a full street address is not needed.
- Optional: tag convention, rug border, clearances, budget allocations, vendor lead times, and buffer.

Ask once in a consolidated list for missing inputs. If instructed to proceed, mark gaps "MISSING — confirm" and list them under Questions for the client; never guess quantities, dimensions, dates, or currency. Proposed budget allocations are permitted only as clearly labeled estimates, not product prices.

## Procedure
1. Extract the brief's figures and constraints without changing them.
   - Preserve quantities, dimensions, budget, currency, dates, and units.
   - Show any unit conversion separately; flag ambiguous dates or conflicting figures.
2. Create an inventory of every requested item and every existing piece to keep.
   - Give each a unique tag; use the supplied convention or simple sequential tags.
   - Distinguish a requested purchase from an existing piece that may fulfill it; ask if unclear.
   - Preserve missing quantities as missing, rather than assuming one.
3. Create one schedule row per inventory entry, retaining all requested items.
   - Use status "new" or "existing-reuse"; flag ambiguous ownership for confirmation.
   - Mark retained existing pieces "existing-reuse" and request missing measurements.
   - Do not assume reuse is cost-free: separate purchase allowance from handling, repair, or upholstery work.
4. Apply likes and dislikes before writing material notes.
   - State "Excluded per client: …" under Design intent.
   - Repeat each exclusion in affected rows; do not specify the disliked material, finish, or style.
   - For a conflicting request, retain a neutral item row marked "HOLD — client conflict"; ask for resolution.
5. Enter target sizes only when supported by supplied dimensions and sizing criteria.
   - For a rug with a supplied border: length = room length − 2 × border; width = room width − 2 × border.
   - Show both substitutions and results, with consistent units, in the target-size cell.
   - For other derived sizes, show the supplied constraint and arithmetic.
   - Without a border, clearance, or measurement needed for sizing, write "MISSING — designer to size."
   - Flag nonpositive results or conflicts with openings, furniture, or circulation; do not call a size a confirmed fit.
6. Translate users and pets into row-specific requirements to verify.
   - For children, consider rounded/eased edges and stability verification.
   - For pets or frequent spills, request cleanability and suitable upholstery durability verification.
   - Phrase all notes as requirements, such as "cleanable upholstery required — verify manufacturer cleaning code."
   - Do not imply a product has these properties or satisfies an accessibility requirement.
7. Restate the client's total budget and scope exactly.
   - Retain supplied allocations; otherwise propose provisional allocations only within the stated budget and currency.
   - Label row amounts "allowance/estimate — confirm with quotes" and identify whether each is a unit or extended amount.
   - Where unit allowances are used, show quantity × unit allowance = row total.
   - Separate contingency and costs not allocated to rows; avoid double counting.
   - Show known row totals + other allowances + contingency = allocated total.
   - Show client budget − allocated total = unallocated balance or shortfall; do not force equality.
   - Mark unknown costs and scope explicitly; an apparent balance is not confirmation of budget sufficiency.
   - Without a total or currency, leave monetary allocations "MISSING — confirm"; never invent product prices or identities.
8. Check timing against the install date.
   - If install and reference dates are supplied, show install date − reference date = calendar days, then days ÷ 7 = weeks.
   - Otherwise mark the timing calculation missing; do not introduce a date.
   - For each new item and any work on reuse items, show order-by logic: install date − lead time − buffer.
   - Calculate a date only with supplied durations and a clear calendar/business-day basis; label assumptions and estimates.
   - If an input is missing, retain the formula and mark feasibility unconfirmed; ask for vendor confirmation.
   - Flag order-by dates before the reference date; prioritize any identified custom or made-to-order items.
9. Build a tag-specific Specs to verify list.
   - Address flammability, abrasion/double rubs, cleaning codes, and slip resistance for relevant materials and uses.
   - Request manufacturer data and test-method context; never assert a rating or compliance as fact.
   - If a category seems inapplicable, state why for professional review rather than silently omitting it.
   - For reuse items without documentation, flag the evidence gap for professional assessment.
10. Generate the six output sections in the order below.
    - Include every missing input, request/dislike conflict, unverified timing input, and budget-scope gap in client questions.
    - Identify vendor or professional follow-up separately within the relevant check sections.
11. Reconcile the finished draft against the inventory.
    - Confirm every request and retained piece has a row, quantities match, and reuse statuses are correct.
    - Check dislike exclusions, arithmetic, allowance labels, timing gaps, and tag-specific performance requirements.
    - Remove unsupported product identities, prices, dates, ratings, compliance claims, and citations.

## Output format
```markdown
## Design intent
[Room use, users/pets, likes, and requirements. Excluded per client: …; unresolved conflicts: …]
## FF&E schedule
| Tag | Item | Qty | Target size (show derived calculation) | Material / performance notes (verify) | Budget allowance/estimate — confirm with quotes | Lead-time check / order-by | Status |
|---|---|---|---|---|---|---|---|
| [tag] | [item] | [qty or MISSING] | [size/calculation or MISSING] | [requirements and exclusions] | [extended allowance or MISSING] | [date/formula, missing inputs, feasibility] | [new / existing-reuse] |
## Budget check
Client total: [exact amount/currency or MISSING]. Scope: [supplied scope and gaps].
[row totals] + [other allowances] + [contingency] = [allocated total]; budget − allocated total = [balance/shortfall].
[Unknown costs; all allocations are allowances/estimates to confirm with quotes.]
## Lead-time check
[Install − reference date = days; days ÷ 7 = weeks, or missing inputs.]
[Tag-specific order-by estimates/formulas, overdue risks, and vendor confirmations required.]
## Specs to verify
[By tag: applicable manufacturer-data checks; reasons for apparent nonapplicability; professional follow-up.]
## Questions for the client
[Numbered missing inputs and conflicts; distinguish client decisions from vendor/professional checks.]
```

## Hard limits
- Never invent products, names, model numbers, prices, stock availability, lead times, ratings, or compliance claims.
- Do not introduce unsupported laws, article numbers, regulators, dates, URLs, statistics, or citations. No official sources are supplied for citation.
- No official AI-specific guidance was verified for this profession. Check with your licensing body or regulator.
- Fire/flammability codes for furnishings depend on project type and jurisdiction; the designer must confirm applicable requirements.
- A licensed professional where required, or the responsible professional in the jurisdiction, must verify measurements, fit, circulation, performance evidence, applicable requirements, budget scope, quotes, and delivery feasibility before issue or procurement.
- UK/AU practitioners must verify their local requirements; do not assume US requirements apply.
- Contract and procurement terms are the studio's; do not invent or assume them.
- Never silently omit requests or specify disliked features; hold unresolved conflicts for client approval.
- Privacy: de-identify briefs before use; remove names, addresses, access codes, and identifying images or metadata. Use only studio-approved tools for client data and include only information needed for the task.
- Before issue or procurement, see references/checklist.md.

## Example
Input (fictional):
```text
Sample Room: 12 × 16 ft; wants 1 rug with a 2 ft border on every side.
Keep 1 existing wood side table, 20 × 20 × 22 in; no work needed.
One dog; likes blue; dislikes velvet. Proceed with missing inputs flagged.
Budget: USD 1,200 including all costs; rug allowance 900, handling 100, contingency 200.
```
Output (abbreviated):
```markdown
## Design intent
Blue accents; dog-related cleanability to verify. Excluded per client: velvet.
## FF&E schedule
| Tag | Item | Qty | Target size | Notes (verify) | Allowance/estimate — confirm with quotes | Lead-time / order-by | Status |
|---|---|---|---|---|---|---|---|
| 01 | Rug | 1 | 12−2×2 = 8 ft; 16−2×2 = 12 ft | No velvet; cleanability and slip resistance required | USD 900 extended | Install − lead − buffer; inputs missing | new |
| 02 | Wood side table | 1 | 20 × 20 × 22 in, supplied | Verify condition/stability; no velvet additions | USD 0 purchase; handling below | Handling timing missing | existing-reuse |
## Budget check
Client total USD 1,200, all costs: 900 + 0 + 100 handling + 200 contingency = 1,200; balance 0. Estimates to confirm with quotes; tax/freight coverage unverified.
## Lead-time check
Install/reference dates and lead/buffer durations missing; feasibility unconfirmed.
## Specs to verify
01: manufacturer flammability, abrasion/test method, cleaning instructions and slip data; professional confirms applicability. 02: verify cleaning instructions; upholstery abrasion/code apparently inapplicable to wood; professional assesses fire/slip relevance and missing documentation.
## Questions for the client
1. Project type/jurisdiction? 2. Install/reference dates and handling plan? 3. Vendor lead time and planning buffer? 4. How are tax/freight covered?
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

DRAFT FF&E SCHEDULE: FAMILY ROOM, EXAMPLE FAMILY (FICTIONAL)
Status: draft for professional review. No products, prices, ratings, or compliance are confirmed.

I drafted with gaps flagged rather than holding for inputs. Items marked "MISSING — confirm" are collected in the questions at the end.


DESIGN INTENT

Use: family room, 16 ft x 20 ft (192 x 240 in), 9 ft ceiling. One 8 ft wide window on the north wall. Door locations and other openings are MISSING — confirm.

Users: two children (ages 4 and 7) and one large dog that sheds. Row requirements:
  - Child safety: rounded or eased edges, stability, and tip-over checks.
  - Dog: hair release, cleanability, and abrasion durability.

Likes: warm wood, oatmeal tones.

Excluded per client: glass tabletops, velvet.

Unresolved conflicts: none identified.


FF&E SCHEDULE

Tag convention: none supplied, so tags are sequential (01–07).

01  Sectional sofa (seats 6)
    Qty: 1 (stated singular; confirm)
    Target size: MISSING — designer to size. Seating for 6 within a 16 x 20 ft room. Configuration, clearances, and door locations are needed.
    Notes (verify): oatmeal-tone upholstery. No velvet. Cleanable upholstery required; verify the manufacturer cleaning code. Durability suited to a large shedding dog and children; verify abrasion data and test method. Fabric should release pet hair; verify with a sample.
    Allowance: USD 9,500 extended (allowance/estimate — confirm with quotes)
    Lead time: upholstery 14–16 wk quoted. Order-by = Mar 15, 2027 − lead − buffer (see Lead-time check).
    Status: new

02  Area rug
    Qty: 1 (stated singular; confirm)
    Target size, from the 18 in border on every side:
      length = 240 in − 2 x 18 in = 204 in (17 ft)
      width  = 192 in − 2 x 18 in = 156 in (13 ft)
      Result: 13 x 17 ft. This is not a confirmed fit.
    Size flags: the rug will run under or near the sectional, chairs, and console, so verify placement and door swings. A 13 x 17 ft rug may not be a stock size and may need custom or made-to-order work.
    Notes (verify): oatmeal or warm tones. No velvet. Cleanable, with dog-hair removal and spill tolerance; verify the cleaning instructions. A low or flat pile may suit shedding; designer to confirm. Rug pad and slip resistance required; verify manufacturer data.
    Allowance: USD 4,000 extended (estimate — confirm with quotes)
    Lead time: MISSING. Treat as custom-risk until a vendor confirms.
    Status: new

03  Coffee table
    Qty: 1 (stated singular; confirm)
    Target size: MISSING — designer to size relative to the sectional and circulation.
    Notes (verify): warm wood preferred. No glass tabletop. Rounded or eased edges required for children. Stability verification required. Finish should resist scratches from the dog and children; verify finish data and cleaning instructions.
    Allowance: USD 1,800 extended (estimate — confirm with quotes)
    Lead time: MISSING
    Status: new

04  Lounge chairs
    Qty: 2
    Target size: MISSING — designer to size.
    Notes (verify): oatmeal-tone upholstery. No velvet. Cleanable upholstery; verify the cleaning code. Abrasion durability and pet-hair release; verify. Stability required.
    Allowance: 2 x USD 2,200 = USD 4,400 extended (estimate — confirm with quotes)
    Lead time: assumed to fall under the upholstery quote of 14–16 wk; confirm.
    Status: new

05  Floor lamps
    Qty: 2
    Target size: MISSING — designer to size. The 9 ft ceiling is the upper limit.
    Notes (verify): warm wood or tone-compatible finish. No velvet shades. A weighted, stable base is required because of the children and a large dog; verify tip resistance. Cord routing and management required. Electrical listing and certification must be verified for the jurisdiction.
    Allowance: 2 x USD 450 = USD 900 extended (estimate — confirm with quotes)
    Lead time: MISSING
    Status: new

06  Drapery for the north window
    Qty: MISSING — confirm number of panels, pair or single, and whether hardware is included.
    Target size: MISSING — designer to size. Known constraints are an 8 ft wide window and a 9 ft ceiling. Window height, sill, mount height, stack-back, and fullness are needed.
    Notes (verify): oatmeal tones. No velvet. Cleanability required (pets and children); verify cleaning instructions. Cord and chain safety for young children must be verified against local requirements. Fabric flammability must be verified for the jurisdiction and project type.
    Allowance: USD 2,600 extended, covering fabric, fabrication, and hardware (estimate — confirm with quotes)
    Lead time: MISSING. If custom-fabricated, prioritize.
    Status: new

07  Walnut media console, for the existing 75 in TV
    Qty: 1 (confirm)
    Target size: MISSING — supply W x D x H. Verify that the top supports the TV stand footprint and weight, or confirm the TV is wall-mounted.
    Notes (verify): condition and stability. Anti-tip anchoring required given the children; professional to assess. No glass top additions. Finish cleanability.
    Allowance: USD 0 purchase. Handling is listed under the Budget check. Any repair or refinish work is MISSING — confirm.
    Lead time: handling and work timing MISSING
    Status: existing-reuse


BUDGET CHECK

Client total: $28,000 for all FF&E, including tax and delivery. Currency is assumed to be USD; confirm.

Scope gaps: installation, design fees, drapery hardware installation, and contingency were not stated.

Row totals (provisional):
  9,500 + 4,000 + 1,800 + 4,400 + 900 + 2,600 = 23,200

Other allowances:
  Delivery and receiving: 1,200
  Console handling: 150
  Sales tax: MISSING. The rate depends on the jurisdiction.

Contingency: 1,400

Allocated total:
  23,200 + 1,350 + 1,400 = 25,950

Balance:
  28,000 − 25,950 = 2,050 unallocated

The balance covers tax only if effective tax is at most about 8.8% of the 23,200 in row totals (2,050 ÷ 23,200). A higher rate creates a shortfall.

All figures are allowances or estimates to confirm with quotes. An apparent balance does not confirm the budget is sufficient. Custom rug pricing and drapery quantity are the largest unknowns.


LEAD-TIME CHECK

Reference date: not supplied. I used today's date, Oct 19, 2026, as an assumed reference; confirm.

Days to install:
  Mar 15, 2027 − Oct 19, 2026 = 147 calendar days
  147 ÷ 7 = 21 weeks

Upholstery (01, 04) order-by. Basis: calendar weeks, assuming the quote runs to delivery on site (confirm). Buffer is MISSING.
  16 wk: Mar 15, 2027 − 112 days = Nov 23, 2026, minus buffer
  14 wk: Mar 15, 2027 − 98 days  = Dec 7, 2026, minus buffer
  At worst case, about 5 weeks of slack remain before any buffer. A buffer longer than 5 weeks would put the order-by date before the reference date.

  Example: a 4-week buffer gives an order-by of Oct 26, 2026, which means approvals are needed within a week.

Rug (02) and drapery (06): order-by = Mar 15, 2027 − lead − buffer. Both inputs are missing and both are likely custom. Prioritize vendor confirmation now.

Coffee table (03) and lamps (05): formula as above; vendor lead times missing.

Console (07): any work or handling must be completed before install; timing missing.

Vendor confirmations required for all rows:
  - lead time for every non-upholstery item
  - whether the upholstery quote includes freight or transit
  - calendar-day versus business-day basis
  - stock status

Feasibility is unconfirmed for all items.


SPECS TO VERIFY

Fire and flammability requirements depend on project type and jurisdiction, and the designer must confirm them. No ratings are asserted here.

01 Sectional, 04 Lounge chairs
  - Upholstery flammability data and test method
  - Abrasion (double rubs) and test method
  - Cleaning code
  - Pet-hair release and pilling (sample test)
  - Frame stability
  - Slip resistance: likely not applicable; professional to confirm leg glides and floor protection.

02 Rug
  - Flammability and the applicable test method
  - Abrasion and wear data
  - Cleaning instructions
  - Slip resistance with pad
  - Edge trip hazard

03 Coffee table
  - Finish durability and cleaning instructions
  - Edge profile
  - Stability
  - Flammability and abrasion: likely limited for solid wood with no upholstery; professional to confirm.

05 Floor lamps
  - Electrical certification for the jurisdiction
  - Base stability and tip testing
  - Shade material flammability
  - Abrasion and slip: apparently not applicable; confirm.

06 Drapery
  - Fabric flammability for project type and jurisdiction
  - Cleaning instructions and shrinkage
  - Cord safety requirements
  - Abrasion and slip: apparently not applicable; confirm.

07 Media console (reuse)
  - No documentation supplied, which is an evidence gap.
  - Professional to assess structural condition, load capacity for the TV, anti-tip anchoring, and finish cleanability.


QUESTIONS FOR THE CLIENT

Client decisions:
  1. Is the currency USD? Do installation and design fees fall within the $28,000?
  2. Do you accept the provisional allocations and contingency, or do you have your own split?
  3. What are the drapery quantity and style: panel count, single or pair, mount, and length? Is hardware included?
  4. Please confirm quantities of 1 for the sectional, rug, coffee table, and console.
  5. Should the sectional be a specific configuration (L, U, chaise), with a preferred orientation to the TV?
  6. Does the console need any repair or refinish? What are its dimensions? Is the TV on the console or wall-mounted?
  7. Where are the doors and other openings? What are the window height and sill?

Designer, vendor, and professional checks:
  8. What is the project type and jurisdiction, for tax and flammability requirements?
  9. What scheduling reference date and planning buffer should be used?
  10. Lead times for the rug, drapery, coffee table, and lamps. Does the upholstery quote include freight, and is it in calendar weeks?
  11. Confirm that 13 x 17 ft is available, or the custom cost and timing for it.
  12. Verify all measurements, fit, and circulation on site before issue or procurement.

Before issue or procurement, run through references/checklist.md and de-identify the brief for your records.

