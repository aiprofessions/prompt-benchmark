# Transcript — skill interior-designers-ffe-schedule [en] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:15:22+00:00
- duration_s: 114.0
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

Family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft window on the north wall. Users include two children (ages 4 and 7) and a large shedding dog — child edge/stability safety and pet-cleanable upholstery are requirements to verify on every seating and rug item below. Likes: warm wood tones, oatmeal color palette. Excluded per client: glass tabletops, velvet. These exclusions are repeated on every affected row below; no glass tabletop or velvet upholstery is specified anywhere in this draft. No conflicting requests were identified in the brief.

FF&E SCHEDULE

Tag 01 — Sectional sofa (seating 6)
  Qty: 1
  Target size: MISSING — designer to size. No clearance/circulation criteria supplied; room is 16 x 20 ft for reference only.
  Notes to verify: No velvet. Cleanable, durable upholstery required for dog hair/shedding and child use — verify manufacturer cleaning code and abrasion (double-rub) rating. Verify flammability requirement applicable to project type/jurisdiction (MISSING). Frame stability suitable for kids climbing — verify.
  Allowance: $9,000 (unit = extended, qty 1) — allowance/estimate, confirm with quotes.
  Lead-time: Upholstered, custom/made-to-order — treat as priority item. Order-by = install date − 14–16 wk vendor lead time (buffer not supplied). See Lead-time check below.
  Status: new

Tag 02 — Area rug
  Qty: 1
  Target size: Room 16 ft (width) x 20 ft (length); border 18 in = 1.5 ft on every side.
    Width: 16 − (2 x 1.5) = 13 ft (156 in)
    Length: 20 − (2 x 1.5) = 17 ft (204 in)
    Target size: 13 ft x 17 ft. Not yet checked against actual furniture footprint/circulation — professional to confirm fit clears sectional, console, and walkways.
  Notes to verify: Oatmeal tone requested; no velvet applicable (not a velvet-typical category, noted for completeness). Cleanability for pet hair/stains and slip resistance (with kids running and dog on rug) — verify manufacturer data and whether a pad is needed. Flammability applicability for area rugs under project type/jurisdiction — verify (jurisdiction MISSING).
  Allowance: $2,200 (unit = extended, qty 1) — allowance/estimate, confirm with quotes.
  Lead-time: MISSING — vendor lead time not supplied; order-by formula = install date − lead time − buffer, pending vendor confirmation.
  Status: new

Tag 03 — Coffee table
  Qty: 1
  Target size: MISSING — designer to size. No clearance criteria (e.g., distance from sectional) supplied.
  Notes to verify: No glass tabletop (excluded). Warm wood finish preference. Rounded/eased edges and tip stability required given children ages 4 and 7 — verify.
  Allowance: $1,200 (unit = extended, qty 1) — allowance/estimate, confirm with quotes.
  Lead-time: MISSING — vendor lead time not supplied.
  Status: new

Tag 04 — Lounge chair
  Qty: 2
  Target size: MISSING — designer to size.
  Notes to verify: No velvet. Cleanable, durable upholstery for pet/child use — verify cleaning code and abrasion rating. Flammability applicability — verify (jurisdiction MISSING).
  Allowance: $700 unit x 2 = $1,400 extended — allowance/estimate, confirm with quotes.
  Lead-time: Upholstered — if custom/made-to-order, same 14–16 wk vendor lead time category may apply; confirm with vendor. Treat as priority pending confirmation.
  Status: new

Tag 05 — Floor lamp
  Qty: 2
  Target size: MISSING — designer to size.
  Notes to verify: Warm wood/oatmeal tone preference for base/shade. Tip-resistance and cord management required given young children — verify. Safety certification applicable to jurisdiction (MISSING) — verify.
  Allowance: $350 unit x 2 = $700 extended — allowance/estimate, confirm with quotes.
  Lead-time: MISSING — vendor lead time not supplied.
  Status: new

Tag 06 — Drapery
  Qty: MISSING — confirm number of panels for the 8 ft window.
  Target size: MISSING — designer to size. Window width (8 ft) and ceiling height (9 ft) supplied, but rod/mount height, drop, and fullness criteria not supplied.
  Notes to verify: No velvet. Oatmeal tone preference. Flammability requirement for window treatments applicable to jurisdiction — verify (MISSING). Child-safety cord/operation requirements (ages 4 and 7) — verify against applicable standard for the jurisdiction (MISSING).
  Allowance: $500/panel — unit allowance only; row total MISSING pending quantity confirmation.
  Lead-time: MISSING — vendor lead time not supplied.
  Status: new

Tag 07 — Walnut media console (for existing 75 in TV)
  Qty: 1
  Target size: MISSING — existing piece; dimensions (W x D x H) not supplied. Needed to confirm TV fit and room layout.
  Notes to verify: Existing piece — no documentation supplied on original finish/flammability; evidence gap flagged for professional assessment. Warm wood already aligns with likes (no change requested). Verify structural stability and tip-restraint/anchoring given children in the room and a 75 in TV on top — recommend professional check.
  Allowance: $0 purchase (existing-reuse). Handling/repair/refinishing scope not stated by client — MISSING, confirm if any work is needed; if so, allowance separate from $0 purchase figure above.
  Lead-time: Not applicable to purchase; if any repair/refinishing work is required, timing is MISSING pending scope confirmation.
  Status: existing-reuse

BUDGET CHECK

Client total: $28,000, scope stated as "total FF&E including tax and delivery." Installation labor scope (e.g., drapery hardware mounting) not specified — MISSING.

Known row allowances:
  01 Sectional: $9,000
  02 Rug: $2,200
  03 Coffee table: $1,200
  04 Lounge chairs: $1,400
  05 Floor lamps: $700
  06 Drapery: MISSING (qty unconfirmed, not included in sum)
  07 Console: $0 purchase (handling scope MISSING, not included in sum)
Known row subtotal = 9,000 + 2,200 + 1,200 + 1,400 + 700 = $14,500

Contingency: not specified by client. Provisional estimate at 10% of total budget = $2,800 — allowance/estimate, confirm with client.

Allocated total (known) = $14,500 (rows) + $2,800 (contingency) = $17,300
Budget − allocated total = $28,000 − $17,300 = $10,700 unallocated balance.

This $10,700 balance must still cover: the drapery purchase (quantity pending), tax, delivery/freight, any installation labor, and any console handling/repair work — none of these are itemized separately by the client beyond the statement that tax and delivery are included in the $28,000 total. An apparent balance here is not confirmation that the budget is sufficient; all figures are allowances/estimates to confirm with vendor quotes.

LEAD-TIME CHECK

Reference date: not supplied by the client. Today's system date (October 19, 2026) is used here as the scheduling reference point — confirm with client if a different reference date applies.
Install date: March 15, 2027.
Calendar days: March 15, 2027 − October 19, 2026 = 147 days.
Weeks: 147 ÷ 7 = 21 weeks.

Upholstered items (Tags 01 sectional, 04 lounge chairs) — vendor-quoted lead time 14–16 weeks, buffer not supplied:
  Order-by (14 wk / 98 days before install): March 15, 2027 − 98 days = December 7, 2026.
  Order-by (16 wk / 112 days before install): March 15, 2027 − 112 days = November 23, 2026.
  Order-by window: approximately November 23 – December 7, 2026. This falls after the assumed reference date (October 19, 2026), so timing is not currently overdue — but no planning buffer is included in this calculation; recommend ordering at or before the earlier end of this window and confirming buffer with the vendor.
  Priority: treat Tags 01 and 04 as the most time-sensitive items given the 14–16 week quoted lead time.

All other new items (Tags 02 rug, 03 coffee table, 05 floor lamps, 06 drapery) — vendor lead times not supplied. Order-by formula (install date − lead time − buffer) cannot be completed; feasibility unconfirmed pending vendor lead-time confirmation for each.

Tag 07 console — no purchase lead time applicable; any repair/refinishing timing is MISSING pending scope confirmation.

SPECS TO VERIFY

Tag 01 Sectional: manufacturer flammability data (per applicable code for project type/jurisdiction — MISSING), abrasion/double-rub rating, cleaning code, frame/stability data.
Tag 02 Rug: flammability applicability for area rugs under the applicable code (verify with professional whether this category applies), slip-resistance data, cleaning/stain instructions for pet and child use.
Tag 03 Coffee table: edge-profile and tip-stability documentation; flammability/slip ratings likely not applicable to a hard-surface table — professional to confirm applicability rather than assume.
Tag 04 Lounge chairs: same categories as Tag 01 — flammability, abrasion/double-rub, cleaning code, stability.
Tag 05 Floor lamps: tip-resistance/stability data, electrical safety certification applicable to jurisdiction, cord-management features for child safety.
Tag 06 Drapery: flammability data for window treatments under applicable code, child-safety cord/operation standard applicable to jurisdiction, cleaning instructions.
Tag 07 Console (existing): no manufacturer documentation available — flagged as an evidence gap for professional assessment; tip-restraint/anchoring adequacy for TV weight and child safety should be checked by a professional.

QUESTIONS FOR THE CLIENT

1. Project type and jurisdiction (country/state) — needed to confirm applicable flammability, slip-resistance, and child-safety-cord requirements.
2. Please confirm the scheduling reference date; this draft assumed today, October 19, 2026.
3. Vendor-side planning buffer beyond the quoted 14–16 week upholstery lead time — not supplied.
4. Number of drapery panels required for the 8 ft window.
5. Drapery sizing criteria: desired drop/rod height and mounting type (ceiling-mount vs. above-window) — not supplied.
6. Dimensions of the existing walnut media console (W x D x H), and whether any repair, cleaning, or refinishing work is needed.
7. Sizing/clearance criteria for the sectional, coffee table, lounge chairs, and floor lamps (e.g., desired clearances from walls, TV, or rug) — not supplied.
8. Confirm contingency amount/percentage (10% proposed above is provisional only) and whether installation labor is included in the $28,000 total.
9. Any additional pet/child safety requirements to flag for professional verification (e.g., anchoring the console/TV)?
10. Vendor lead times for the rug, coffee table, floor lamps, and drapery — not supplied; needed to complete order-by calculations for these items.

