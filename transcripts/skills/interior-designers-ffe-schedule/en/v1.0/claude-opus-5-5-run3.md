# Transcript — skill interior-designers-ffe-schedule [en] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:10:59+00:00
- duration_s: 85.7
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

Family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft wide window on the north wall. Door locations, window height/sill, other openings, and the fireplace/built-in status are not supplied.

Users are two children (ages 4 and 7) and a large dog that sheds. Requirements to verify:
- Eased or rounded edges and stability on low and tall pieces.
- Tip-over restraint where needed.
- Cleanable, durable upholstery and rug.
- Hair-release performance on fabrics.
- Child-safe window covering operation.

Likes: warm wood, oatmeal tones.
Excluded per client: glass tabletops, velvet.
Unresolved conflicts: none direct. Light oatmeal tones may show soil and dog hair. This needs a client decision (question 12).

FF&E SCHEDULE

Tags are sequential because no tag convention was supplied. All amounts are allowance/estimate, confirm with quotes. Currency is shown as "$" because the brief does not state the currency (question 1).

01  Sectional sofa, seats 6
    Qty: MISSING, confirm. The brief gives seating capacity (6) but no unit count.
    Target size: MISSING, designer to size. The constraints are the 16 x 20 ft room and 13 x 17 ft rug (see 02). No clearances are supplied.
    Notes (verify):
    - No velvet.
    - Cleanable upholstery required. Verify the manufacturer cleaning code.
    - Abrasion/double-rub data and test method required.
    - Hair-release, low-snag fabric required.
    - Kid-proof stability and frame verification.
    - Warm wood or oatmeal palette per client.
    Allowance: $9,000 extended, provisional.
    Lead time: upholstery quote is 14–16 weeks. Order-by = install − 16 wk − buffer. See Lead-time check.
    Status: new

02  Area rug
    Qty: MISSING, confirm. The brief is singular but gives no number.
    Target size: border 18 in = 1.5 ft.
    - Length: 20 − 2 x 1.5 = 17 ft
    - Width: 16 − 2 x 1.5 = 13 ft
    - Result: 13 x 17 ft (156 x 204 in)
    Not a confirmed fit. Check against door swings, hearth, floor vents, and circulation. Locations are not supplied.
    Notes (verify):
    - No velvet pile.
    - Cleanability and stain/soil performance required.
    - Slip resistance required (children). The rug pad is not in the brief (question 9).
    - Shedding and pet-hair cleanup to verify.
    Allowance: $3,500 extended, provisional.
    Lead time: MISSING. This size may require custom or made-to-order production. Confirm with the vendor and prioritize if custom.
    Status: new

03  Coffee table
    Qty: MISSING, confirm.
    Target size: MISSING, designer to size. No clearance criteria are supplied.
    Notes (verify):
    - Excluded per client: glass tabletop.
    - Warm wood preferred.
    - Rounded or eased edges required (children).
    - Stability verification.
    - Finish cleanability and scratch durability (pet claws) to verify.
    Allowance: $1,800 extended, provisional.
    Lead time: MISSING. Order-by = install − lead − buffer. Feasibility unconfirmed.
    Status: new

04  Lounge chair
    Qty: 2
    Target size: MISSING, designer to size.
    Notes (verify):
    - No velvet.
    - Cleanable upholstery required. Verify the cleaning code.
    - Abrasion data and test method required.
    - Hair-release fabric required.
    - Tip and stability verification (children climbing).
    - Exposed wood per client palette.
    Allowance: 2 x $1,800 = $3,600 extended, provisional.
    Lead time: if upholstered, 14–16 weeks per vendor quote. Order-by = install − 16 wk − buffer. Confirm the quote applies to this item.
    Status: new

05  Floor lamp
    Qty: 2
    Target size: MISSING, designer to size. The 9 ft ceiling is supplied.
    Notes (verify):
    - Weighted base and tip stability required (children, large dog).
    - Cord management required.
    - Electrical certification applicable in the jurisdiction to verify.
    - No velvet shades.
    Allowance: 2 x $450 = $900 extended, provisional.
    Lead time: MISSING. Feasibility unconfirmed.
    Status: new

06  Drapery, north window
    Qty: 1 window. Panel count and fullness are MISSING.
    Target size: width 8 ft is supplied. Window height, sill, mounting height, stack-back, and returns are MISSING, designer to size. The 9 ft ceiling caps the maximum mount height.
    Notes (verify):
    - No velvet.
    - Cordless or child-safe operation required. Verify the local window-covering requirements.
    - Fabric flammability data required.
    - Cleanability required.
    - Lining and light control not specified.
    Allowance: $2,200 extended, provisional. Whether this includes hardware and installation must be confirmed.
    Lead time: MISSING. Custom drapery is typically made to order. Confirm with the workroom.
    Status: new

07  Walnut media console, for the existing 75 in TV
    Qty: MISSING, confirm. The brief is singular.
    Target size: MISSING. Measure W x D x H, and confirm it suits the TV's actual width and stand footprint.
    Notes (verify):
    - Condition and stability check.
    - Anti-tip anchoring for the console and TV (children).
    - Finish cleanability.
    - Work needed not stated.
    Allowance: $0 purchase. Handling and anchoring are under other allowances. Repair/refinish is MISSING.
    Lead time: timing for any handling or refinishing is MISSING.
    Status: existing-reuse

BUDGET CHECK

Client total: $28,000 (currency to confirm).
Scope supplied: total FF&E including tax and delivery.
Not stated: installation and receiving, drapery hardware and install, design fees, contingency, and rug pad.

Row totals (provisional):
9,000 + 3,500 + 1,800 + 3,600 + 900 + 2,200 + 0 = $21,000

Other allowances (provisional):
- Tax + delivery: $3,500. The tax rate and jurisdiction are MISSING, so this is not calculated and may be insufficient.
- Item 07 handling and anchoring: $250.

Contingency (provisional): $2,800

Allocated total:
21,000 + 3,500 + 250 + 2,800 = $27,550

Balance:
28,000 − 27,550 = $450 unallocated.

All figures are allowances/estimates to confirm with quotes. They are not product prices. The apparent balance does not confirm the budget is sufficient, because the tax rate, delivery quotes, install scope, and console work are unknown.

LEAD-TIME CHECK

Install date: March 15, 2027. Reference date: MISSING (question 4).

Illustrative only, if the reference date is the session date 2026-10-19:
- Mar 15 2027 − Oct 19 2026 = 147 calendar days
- 147 ÷ 7 = 21 weeks

Upholstery (01, and 04 if upholstered), calendar-day basis, before buffer:
- 16 weeks (112 days): order by Nov 23, 2026, minus buffer.
- 14 weeks (98 days): order by Dec 7, 2026, minus buffer.
- Use the 16-week date. Buffer is MISSING.
- Against the illustrative 21 weeks, the margin is 5 weeks before buffer, decisions, approvals, and deposits.

Vendor confirmations needed:
- Does "14–16 weeks" mean production only or to delivery?
- Does it apply to both 01 and 04?
- Is it calendar-based or business-day based?

Items 02, 03, 05, and 06: lead times MISSING. Formula retained (install − lead − buffer); feasibility unconfirmed. Prioritize 02 and 06 if custom.

Item 07: timing for any work is MISSING.

SPECS TO VERIFY

Flammability requirements depend on project type and jurisdiction, which are not supplied. The responsible professional confirms what applies.

01 and 04:
- Manufacturer flammability data for fabric and fill.
- Abrasion/double-rub results with test method.
- Cleaning code.
- Pilling and hair-release data.
- Slip resistance: not applicable to upholstery itself; check the leg glides on the floor finish.

02:
- Flammability data.
- Pile and fiber cleanability instructions.
- Slip resistance of the rug and pad system.
- Abrasion/wear rating method, if the manufacturer provides one.

03:
- Finish cleaning instructions and durability data.
- Edge profile and stability.
- Abrasion/double rubs: not applicable (no upholstery).
- Flammability: likely low relevance for solid wood. The professional confirms.

05:
- Electrical certification marking applicable in the jurisdiction.
- Stability and tip data.
- Shade material flammability.
- Abrasion and slip: not applicable, except the base footing on the rug.

06:
- Fabric flammability data and test method.
- Cleaning code.
- Child-safety compliance for operating mechanisms (verify local requirements).
- Abrasion: low relevance. Confirm.

07:
- No documentation is supplied. Flag the evidence gap.
- Professional assesses condition, stability, and an anchoring method suitable for the wall construction.
- Abrasion and flammability: apparently not applicable (wood casegood). Confirm.

QUESTIONS FOR THE CLIENT

Client decisions:
1. Confirm the currency of the $28,000 budget.
2. Confirm quantities for the sectional, rug, coffee table, and console. Are they one each?
3. Do installation, receiving, drapery hardware and install, design fees, and contingency sit inside the $28,000?
4. What reference date should timing be measured from, and what planning buffer should be used?
5. What is the project type and jurisdiction (for tax and furnishing requirements)?
6. Where are the doors, vents, fireplace, and outlets? What are the window height and sill?
7. Is the 75 in TV, and its mounting or placement, in FF&E scope?
8. Does the console need any work (repair, refinish, modification)? What are its dimensions?
9. Should a rug pad be added? It is not in the brief but is relevant to slip resistance.
10. Sectional configuration: is there a preferred shape and orientation (facing the TV, the window, or both)?
11. Drapery: what light control or privacy is wanted (lining, blackout, sheer)?
12. Oatmeal tones with two young children and a shedding dog: proceed as is, or accept a performance or deeper-toned variant? What color is the dog's coat?

Vendor and professional checks (not client decisions):
- Scope of the upholstery lead-time quote.
- Lead times for 02, 03, 05, and 06.
- Tax rate.
- Delivery quotes.
- Site measurement and fit confirmation.
- Performance and compliance documentation for every row.

This draft is for professional review before issue or procurement. Measurements, fit, performance evidence, applicable requirements, quotes, and delivery feasibility must be verified, per the studio's checklist (references/checklist.md).

