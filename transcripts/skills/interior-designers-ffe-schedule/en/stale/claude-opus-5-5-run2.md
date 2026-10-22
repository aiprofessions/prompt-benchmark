# Transcript — skill interior-designers-ffe-schedule [en] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:02:25+00:00
- duration_s: 82.1
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

DESIGN INTENT

Family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft wide window on the north wall. Users: two children (ages 4 and 7) and a large dog that sheds. Likes: warm wood and oatmeal tones.

Requirements to verify:
- Rounded or eased edges and stability on tables, lamps, and the console.
- Cleanable, durable upholstery and rug that do not trap dog hair.
- Window treatment that is safe around children, with no accessible looped cords.

Excluded per client: glass tabletops, velvet.

Unresolved conflicts: none between requests and dislikes. Fit, orientation, and circulation are unconfirmed (see questions).

Unit conversion for sizing: 16 ft = 192 in; 20 ft = 240 in.


FF&E SCHEDULE

Tags are simple sequential (01–07); no convention was supplied. All amounts are allowances/estimates to be confirmed with quotes. Amounts are extended (row totals) unless noted.

01  Sectional sofa, seats 6
    Qty: 1 (the brief says "sectional," singular; confirm)
    Target size: MISSING — designer to size. Needs a clearance and circulation rule, wall and opening locations, and TV viewing distance. Confirm whether "seats 6" is the client's count or the manufacturer's nominal count.
    Notes (verify):
      - Cleanable upholstery required; verify manufacturer cleaning code.
      - Tight weave that releases pet hair; verify.
      - Abrasion data required; verify test method.
      - Oatmeal tone; warm wood legs or base if exposed.
      - Excluded per client: velvet.
    Allowance: $9,500
    Lead time: 14–16 wk upholstery quote applies; see Lead-time check.
    Status: new

02  Area rug, 18 in border on every side
    Qty: 1 (the brief says "area rug," singular; confirm)
    Target size:
      Width: 192 − 2 × 18 = 156 in = 13 ft
      Length: 240 − 2 × 18 = 204 in = 17 ft
      Result: 13 ft x 17 ft (156 x 204 in)
    This is not a confirmed fit. Check door swings, hearth, built-ins, and floor vents. The size is non-standard and may need custom or made-to-order fabrication.
    Notes (verify):
      - Cleanable fibre and construction required; verify cleaning instructions.
      - Low-snag construction preferred for dog claws; verify.
      - Slip resistance and rug pad required; verify against the floor type.
      - Oatmeal tones.
      - Excluded per client: velvet.
    Allowance: $3,800 (includes pad)
    Lead time: MISSING; likely custom, so prioritize.
    Status: new

03  Coffee table
    Qty: MISSING — confirm (the brief says "coffee table," singular)
    Target size: MISSING — designer to size. Needs the sectional size, the rug size, and a clearance rule.
    Notes (verify):
      - Warm wood.
      - Rounded or eased edges required for the children.
      - Stability required; verify.
      - Durable, cleanable finish; verify.
      - Excluded per client: glass tabletop, velvet.
    Allowance: $1,800, assuming 1 unit pending confirmation.
    Lead time: MISSING.
    Status: new

04  Lounge chair
    Qty: 2
    Target size: MISSING — designer to size.
    Notes (verify):
      - Same upholstery requirements as 01: cleaning code, hair release, abrasion data.
      - Warm wood frame or legs if exposed.
      - Stability required; verify.
      - Excluded per client: velvet.
    Allowance: 2 × $1,900 = $3,800
    Lead time: 14–16 wk upholstery quote applies if upholstered; confirm.
    Status: new

05  Floor lamp
    Qty: 2
    Target size: MISSING. Needs height and base-diameter criteria.
    Notes (verify):
      - Weighted or wide base required; tip-over stability to verify with children and a large dog.
      - Cord management required.
      - Electrical safety marking applicable in your jurisdiction; verify.
      - Excluded per client: glass shades or components are worth confirming with the client. The dislike was stated for tabletops only.
    Allowance: 2 × $450 = $900
    Lead time: MISSING.
    Status: new

06  Drapery for the 8 ft window, plus hardware
    Qty: MISSING — panel count, and whether one or two-way draw.
    Target size: MISSING — designer to size. Window width is 8 ft (96 in) as supplied. Still needed:
      - Rod extension and stackback
      - Mounting height
      - Window height and sill height
      - Ceiling is 9 ft (108 in); clearance below mounting is not supplied.
    Notes (verify):
      - Child-safe operation required: no accessible looped cords; verify the hardware.
      - Flammability data required; verify.
      - Cleanable fabric; verify cleaning instructions.
      - Oatmeal tones.
      - Excluded per client: velvet.
    Allowance: $2,000 (fabrication and hardware; installation scope unconfirmed)
    Lead time: MISSING; custom fabrication, so prioritize.
    Status: new

07  Walnut media console (existing, for the existing 75 in TV)
    Qty: 1
    Target size: MISSING — dimensions not supplied. Also confirm the TV stand or base footprint fits the console.
    Notes (verify):
      - Condition and stability to verify.
      - Anti-tip anchoring of console and TV required with children and a dog; professional or installer to verify.
      - Excluded per client: no glass or velvet additions.
    Allowance: $0 purchase. Handling and any work are under Budget check, separately.
    Lead time: work or handling timing is MISSING.
    Status: existing-reuse


BUDGET CHECK

Client total: $28,000 total FF&E, including tax and delivery. Currency is shown as "$"; confirm USD.

Scope as supplied: purchases, tax, delivery. Not stated: installation, drapery installation, designer fees, contingency, console handling or work.

Provisional allocations. These are not product prices.

  Row totals:
    9,500 + 3,800 + 1,800 + 3,800 + 900 + 2,000 + 0 = $21,800
  Other allowances:
    Tax + delivery: $3,000 (placeholder; the tax rate depends on jurisdiction)
    Console handling: $200 (work scope unknown)
    Subtotal: $3,200
  Contingency (about 10%): $2,800

  Allocated total:
    21,800 + 3,200 + 2,800 = $27,800
  Balance:
    28,000 − 27,800 = $200 unallocated

What the $200 balance does not confirm:
- The tax amount, which needs the jurisdiction rate applied to quotes.
- Freight on custom items.
- Installation and labour.
- Fees.
- Console work.

These are allowances/estimates only; confirm with quotes. If the coffee table quantity changes, or the rug must be custom, revisit the allocation.


LEAD-TIME CHECK

Reference date: 2026-10-19 (today's draft date; confirm this is your scheduling reference).

  Install − reference: Mar 15, 2027 − Oct 19, 2026 = 147 calendar days
  147 ÷ 7 = 21 weeks

Upholstery (01, 04). The order-by date is install − lead time − buffer. The buffer is MISSING, so the dates below assume zero buffer, in calendar weeks:

  16 wk (112 days): Mar 15, 2027 − 112 days = Nov 23, 2026
  14 wk (98 days):  Mar 15, 2027 − 98 days  = Dec 7, 2026

Plan to the 16-week case. Any buffer moves these dates earlier. That leaves about 5 weeks from today for design approval, fabric sampling, quotes, and deposit.

Feasibility is unconfirmed. Vendors must confirm:
- Whether 14–16 wk means ship date or delivered date.
- Freight transit time.
- Whether the quote applies to both 01 and 04.

Other items:
- 02 rug and 06 drapery: lead times MISSING. These are likely custom or made-to-order, so get vendor lead times this week. An order-by date earlier than today would mean the March install is at risk.
- 03 coffee table and 05 floor lamps: lead times MISSING. Formula retained: Mar 15, 2027 − lead − buffer.
- 07 console: handling or work timing MISSING.


SPECS TO VERIFY

The project type and jurisdiction are not supplied. You must confirm which flammability requirements apply. Do not assume US requirements if the project is in the UK or AU.

01 / 04 upholstered seating
  - Manufacturer flammability data and test method.
  - Abrasion / double-rub data and test method.
  - Cleaning code.
  - Pet-hair and claw performance; request samples.
  - Slip resistance: generally not applicable to seating; confirm floor glides or feet so pieces don't slide or scratch.

02 rug
  - Flammability data.
  - Abrasion or wear rating with method.
  - Cleaning instructions.
  - Slip resistance of the rug-and-pad assembly on the actual floor type.

03 coffee table
  - Finish durability and cleaning instructions.
  - Edge profile and stability.
  - Flammability and abrasion likely inapplicable to solid wood with no upholstery; professional to confirm.
  - Slip resistance not applicable beyond floor protection.

05 floor lamps
  - Electrical safety marking and stability.
  - Abrasion and cleaning codes largely inapplicable; confirm the shade fabric's cleaning and heat-related data.

06 drapery
  - Flammability data; often scrutinized for window treatments, so confirm what applies to this project type.
  - Cleaning instructions.
  - Cord or child-safety performance of the hardware.
  - Abrasion largely inapplicable (not a seating surface).
  - Slip resistance not applicable.

07 console (existing)
  - No documentation supplied; this evidence gap needs professional assessment.
  - Condition, structural stability, anchoring method, and cleaning of the finish.
  - Flammability, abrasion, and slip resistance appear inapplicable to a wood case piece; professional to confirm.

A responsible professional must verify measurements, fit, circulation, performance evidence, applicable requirements, quotes, and delivery before issue or procurement. See references/checklist.md.


QUESTIONS FOR THE CLIENT

Client decisions:
1. Is "$" USD?
2. Does the $28,000 include installation, drapery installation, designer fees, and a contingency? Is a ~10% contingency acceptable?
3. Coffee table quantity: one?
4. Drapery: panel count, one or two-way draw, sheer or lined, and light-control preference?
5. Lounge chairs: upholstered? Any preferred shape?
6. Sectional: is "seats 6" a firm requirement? Any configuration preference (L-shape, chaise)?
7. Does the 75 in TV stay as-is, and on which wall? Does the console need any repair or refinishing?
8. Dislike of glass: tabletops only, or all glass, such as lamp shades and accents?
9. Who handles the console during install, and when?

Designer measurements and inputs:
10. Project type and jurisdiction, to determine flammability and other requirements.
11. Locations and swings of doors and openings. Which wall is north, the 16 ft or the 20 ft? Hearth, vents, built-ins?
12. Window height, sill height, and drapery mounting height.
13. Console dimensions (W x D x H), and the TV base footprint and weight.
14. Floor type, for the rug pad and slip check.
15. Clearance and circulation rules for sizing the sectional, coffee table, and chairs.
16. Scheduling reference date, if not today, and the planning buffer.

Vendor and professional checks:
17. Upholstery: is 14–16 wk to ship or delivered? Freight time? Does it apply to both 01 and 04?
18. Lead times for the custom 13 x 17 ft rug, drapery fabrication, coffee table, and lamps.
19. Applicable tax rate and delivery quotes, to replace the $3,000 placeholder.
20. Manufacturer data and documentation for the items listed under Specs to verify.

