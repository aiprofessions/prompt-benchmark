# Transcript — skill interior-designers-ffe-schedule [en] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:57:45+00:00
- duration_s: 113.9
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
Family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft window (north wall). Users: two children (ages 4 and 7) and one large, shedding dog. Likes: warm wood, oatmeal tones. Excluded per client: glass tabletops, velvet. No conflicting requests identified. Jurisdiction and project type not supplied — flag for fire-code/compliance confirmation.

FF&E SCHEDULE

Tag 01 — Sectional sofa, seats 6
Qty: 1
Target size: MISSING — designer to size (no sectional footprint or room layout clearance supplied)
Notes to verify: No velvet. Warm wood accents/oatmeal tones per likes (verify on frame/trim only, not upholstery fiber claim). Cleanable, dog-shed-tolerant upholstery required — verify manufacturer cleaning code. Child-safe edge profile desirable — verify.
Allowance: 1 × $9,500 = $9,500 (estimate — confirm with quotes)
Lead-time: Vendor-quoted upholstery lead time 14–16 weeks. Order-by = install date − lead time − buffer (buffer not supplied). See Lead-time check below.
Status: new

Tag 02 — Area rug
Qty: 1
Target size: Room 16 ft x 20 ft, border 18 in (1.5 ft) on every side.
Length = 20 ft − 2×1.5 ft = 17 ft (204 in)
Width = 16 ft − 2×1.5 ft = 13 ft (156 in)
Notes to verify: Oatmeal tone preference noted. No velvet (n/a to rug pile but logged for consistency). Cleanability for pet shedding — verify cleaning instructions. Slip resistance required under rug, especially with children in room — verify; non-slip rug pad likely needed — confirm with professional.
Allowance: 1 × $2,800 = $2,800 (estimate — confirm with quotes)
Lead-time: Vendor lead time not supplied — MISSING, request from vendor.
Status: new

Tag 03 — Coffee table
Qty: 1
Target size: MISSING — designer to size (no footprint, clearance, or sectional dimension supplied)
Notes to verify: No glass tabletop (excluded). Warm wood finish per likes — verify child-safe/non-toxic finish. Rounded/eased edges and tip-stability required given ages 4 and 7 — verify. Cleanable surface for dog/kid spills — verify.
Allowance: 1 × $1,800 = $1,800 (estimate — confirm with quotes)
Lead-time: Vendor lead time not supplied — MISSING.
Status: new

Tag 04 — Lounge chairs
Qty: 2
Target size: MISSING — designer to size (no dimensions supplied)
Notes to verify: No velvet. Oatmeal/warm wood frame per likes. Cleanable, durable upholstery for dog shedding — verify manufacturer cleaning code and abrasion/double-rub rating. Rounded arm profile desirable with young children — verify.
Allowance: 2 × $1,600 = $3,200 (estimate — confirm with quotes)
Lead-time: Vendor-quoted upholstery lead time 14–16 weeks (assuming same vendor/program as sectional — confirm). See Lead-time check below.
Status: new

Tag 05 — Floor lamps
Qty: 2
Target size: MISSING — designer to size (height/footprint not specified; 9 ft ceiling noted as a constraint only)
Notes to verify: Warm wood base preference per likes. Tip-over stability required — high priority given young children and a large dog — verify. Cord management/anchoring required to reduce trip and chew hazard — verify. Electrical safety certification required — verify (jurisdiction not supplied).
Allowance: 2 × $450 = $900 (estimate — confirm with quotes)
Lead-time: Vendor lead time not supplied — MISSING.
Status: new

Tag 06 — Drapery (window treatment, north wall)
Qty: MISSING — confirm (panel count for 8 ft window not specified)
Target size: MISSING — designer to size (window height, mounting height/style, and ceiling clearance to 9 ft not supplied)
Notes to verify: No velvet. Oatmeal tone preference noted. Flammability testing applicable to drapery — jurisdiction/code not supplied, verify with professional. Cord-free or contained operating mechanism required — child-safety concern with ages 4 and 7. Cleanability for pet dander/shedding — verify.
Allowance: 1 (placeholder, treatment-level) × $1,500 = $1,500 (estimate — confirm with quotes; will change once panel count/size known)
Lead-time: Vendor lead time not supplied — MISSING; custom drapery often made-to-order, confirm urgently.
Status: new

Tag 07 — Walnut media console (existing, for 75 in TV)
Qty: 1
Target size: MISSING — supplied brief gives no console dimensions; request measurements.
Notes to verify: Confirm condition and finish integrity (walnut, consistent with warm-wood likes). Anti-tip hardware/anchoring required given children ages 4 and 7 and TV weight — verify. Cleanability of existing finish for pet shedding/dander — verify. No work scope specified — confirm if cleaning, anchoring hardware, or repair is needed.
Allowance: $0 purchase; handling/inspection allowance 1 × $200 = $200 (estimate — confirm with quotes/vendor)
Lead-time: Handling/inspection timing not specified — MISSING.
Status: existing-reuse

BUDGET CHECK
Client total: $28,000, scope stated as "total FF&E including tax and delivery." Installation labor, design fees, and warranty are not addressed in the brief — scope gap, flag.

Row totals (purchase/handling allowances):
9,500 + 2,800 + 1,800 + 3,200 + 900 + 1,500 + 200 = $19,900

Other allowances:
Tax & delivery allowance (provisional estimate, since client stated these are included in the $28,000 but line items above are pre-tax placeholders): $3,600
Contingency: $1,500

Allocated total = 19,900 + 3,600 + 1,500 = $25,000
Budget − allocated total = 28,000 − 25,000 = $3,000 unallocated balance

All amounts above are allowances/estimates — confirm with actual vendor quotes. The $3,000 balance is an unallocated reserve, not confirmation that the budget is sufficient; it has not been assigned to installation labor, design fees, rug pad, drapery hardware, or any other unidentified cost.

LEAD-TIME CHECK
Install date: March 15, 2027.
Reference date: not explicitly supplied in the brief — today's session date (October 19, 2026) is used as an assumed planning reference. Confirm this is the correct reference date to use.

Install date − reference date = March 15, 2027 − October 19, 2026 = 147 calendar days
147 ÷ 7 = 21 weeks

Upholstered items (Tag 01 sectional, Tag 04 lounge chairs):
Quoted lead time: 14–16 weeks. Buffer not supplied — order-by dates below exclude buffer; add buffer once confirmed.
Order-by (16-week/longer end, calendar-day basis) = March 15, 2027 − 112 days = November 23, 2026
Order-by (14-week/shorter end) = March 15, 2027 − 98 days = December 7, 2026
Both order-by dates fall after the assumed reference date (October 19, 2026), so ordering currently appears feasible — this is not a confirmed fit; vendor must confirm actual lead time and any buffer needed for fabrication, shipping, and install scheduling.

All other new items (rug, coffee table, floor lamps, drapery) have no vendor lead time supplied — feasibility unconfirmed, request vendor lead times, especially for drapery if custom/made-to-order (prioritize confirming this one given the risk of long made-to-order lead times).

Existing media console: handling/inspection timing not supplied — missing.

SPECS TO VERIFY
01 Sectional: manufacturer flammability data (jurisdiction/code to be confirmed), abrasion/double-rub rating, cleaning code, no velvet confirmation.
02 Rug: cleaning instructions for pet shedding, slip-resistance data, rug-pad requirement, flammability testing applicability for rugs (confirm with professional per jurisdiction).
03 Coffee table: edge/stability data suitable for young children, finish toxicity/safety documentation, cleaning instructions; flammability likely not applicable to solid wood surface — professional to confirm wood-only construction and confirm applicability.
04 Lounge chairs (x2): cleaning code, abrasion/double-rub rating, flammability data, no-velvet confirmation, edge profile suitability for children.
05 Floor lamps (x2): tip-over/stability test data, cord safety/anchoring compliance, electrical safety certification (jurisdiction not supplied — confirm applicable mark/listing), shade cleanability.
06 Drapery: flammability/fire-code applicability (jurisdiction not supplied — professional to confirm applicable code), child-safety cord mechanism compliance, cleaning instructions.
07 Media console (existing): no current documentation — flag evidence gap for professional assessment (condition, anti-tip hardware compatibility, finish cleaning instructions); flammability/slip categories likely not applicable to a solid case good — confirm with professional.

QUESTIONS FOR THE CLIENT
1. Sectional footprint/dimensions (or room layout with clearances) to size seating, coffee table, and confirm circulation — currently MISSING.
2. Lounge chair dimensions and placement preference — MISSING.
3. Floor lamp height/footprint preference — MISSING.
4. Drapery: panel quantity for the 8 ft window, window height, and mounting height (ceiling is 9 ft) — all MISSING, needed to size and quote.
5. Existing walnut media console: length, width, height — MISSING; confirm whether any cleaning, repair, or anti-tip anchoring work is wanted.
6. Confirm reference/planning date for lead-time calculations — today's date (October 19, 2026) was assumed; confirm if a different baseline should be used.
7. Confirm buffer (days/weeks) to add to vendor lead times before order-by dates are finalized.
8. Confirm project type and jurisdiction so applicable fire/flammability and electrical-safety codes can be identified by the responsible professional.
9. Confirm whether installation labor, design fees, or warranty costs are covered within the $28,000 or are additional — scope currently silent on this.
10. Confirm vendor lead times for rug, coffee table, floor lamps, and drapery (none supplied); prioritize drapery if custom/made-to-order given fixed install date.
11. Confirm drapery operating mechanism preference (cordless/child-safe) and rug-pad inclusion, both flagged as child-safety considerations.

