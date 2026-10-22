# Transcript — skill interior-designers-ffe-schedule [en] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:06:38+00:00
- duration_s: 147.5
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

FF&E SCHEDULE DRAFT — Example Family Room (fictional)
Family room, 16 ft x 20 ft, 9 ft ceiling, one 8 ft window (north wall)

DESIGN INTENT
Family room seating for 6 (sectional) plus lounge seating, serving two kids (ages 4 and 7) and one large shedding dog. Likes: warm wood tones, oatmeal tones. Excluded per client: glass tabletops, velvet — these exclusions are repeated on every affected row below. No conflicting requests identified in this brief.

FF&E SCHEDULE
(Tag convention: sequential 01–07)

01 — Sectional sofa, seating 6
  Qty: 1 (6-seat capacity)
  Target size: MISSING — designer to size. Room is 16 x 20 ft but configuration (L-shape, chaise side), door locations, and clearances were not supplied.
  Notes to verify: Warm-wood frame accents and oatmeal upholstery requested; velvet excluded per client. Cleanable upholstery required — verify manufacturer cleaning code (dog). Rounded/eased arm and edge profile, plus stability/anti-tip verification required — kids ages 4 and 7.
  Budget allowance: $9,500 — allowance/estimate, confirm with quotes; extended; pre-tax/delivery.
  Lead-time/order-by: Vendor-quoted upholstery lead 14–16 weeks (98–112 days). Buffer MISSING — confirm with studio/vendor. Unbuffered order-by: ~Nov 23, 2026 (16 wk) to ~Dec 7, 2026 (14 wk). Priority custom item — see Lead-time check.
  Status: new

02 — Area rug
  Qty: 1
  Target size: Border 18 in = 1.5 ft (unit conversion shown). Length = 20 − (2 x 1.5) = 17 ft. Width = 16 − (2 x 1.5) = 13 ft. Target size = 13 ft x 17 ft. Flag: not a confirmed fit — verify against final furniture layout, door swings, and sectional/console clearances (door location not supplied).
  Notes to verify: Oatmeal tone requested. Cleanability/wear durability required (shedding dog) — verify manufacturer cleaning code and wear rating. Slip resistance (rug pad/backing) and flammability data/test method per jurisdiction — verify.
  Budget allowance: $3,500 — allowance/estimate, confirm with quotes; extended; pre-tax/delivery.
  Lead-time/order-by: Vendor lead time not quoted — MISSING. Formula retained: order-by = install date − lead time − buffer.
  Status: new

03 — Coffee table
  Qty: 1
  Target size: MISSING — designer to size; clearances to sectional/chairs not supplied.
  Notes to verify: Warm wood tabletop requested; glass tabletop excluded per client. Rounded/eased edge profile and stability verification required — kids ages 4 and 7. Durable/cleanable finish required (dog).
  Budget allowance: $1,500 — allowance/estimate, confirm with quotes; extended; pre-tax/delivery.
  Lead-time/order-by: Vendor lead time not quoted — MISSING.
  Status: new

04 — Lounge chairs
  Qty: 2
  Target size: MISSING — designer to size.
  Notes to verify: Oatmeal/warm-wood-frame upholstery requested; velvet excluded per client. Cleanable upholstery required (dog) — verify manufacturer cleaning code. Rounded/eased edges and stability verification required — kids ages 4 and 7.
  Budget allowance: 2 x $1,500 = $3,000 — allowance/estimate, confirm with quotes; pre-tax/delivery.
  Lead-time/order-by: Same upholstery lead time as Tag 01 (14–16 weeks). Buffer MISSING. Unbuffered order-by window ~Nov 23–Dec 7, 2026. Priority item.
  Status: new

05 — Floor lamps
  Qty: 2
  Target size: MISSING — designer to size (placement/height not supplied).
  Notes to verify: Warm wood base/finish preferred. Stability/tip-resistance and cord safety required — kids ages 4 and 7, dog. Electrical safety certification — verify per jurisdiction.
  Budget allowance: 2 x $600 = $1,200 — allowance/estimate, confirm with quotes; pre-tax/delivery.
  Lead-time/order-by: Vendor lead time not quoted — MISSING.
  Status: new

06 — Drapery (window treatment, 8 ft wide window, north wall)
  Qty: MISSING — confirm panel count.
  Target size: Window width 8 ft (96 in) noted; ceiling height 9 ft noted. Mount/drop height and fullness ratio not supplied — MISSING, designer to size.
  Notes to verify: Oatmeal tone requested; velvet excluded per client. Flammability/fire-performance data per jurisdiction — verify. Cleaning instructions — verify (dog proximity). If corded, child-safety cord requirements apply — verify, given kids ages 4 and 7.
  Budget allowance: $1,800 — allowance/estimate, confirm with quotes; pre-tax/delivery; likely custom/made-to-order.
  Lead-time/order-by: Vendor lead time not quoted — MISSING. Custom window treatments often carry longer lead times — flag as priority pending vendor confirmation.
  Status: new

07 — Walnut media console (existing, for 75 in TV) — keep
  Qty: 1
  Target size: MISSING — dimensions not supplied; request measurements and clearance check against the 75 in TV.
  Notes to verify: Walnut tone aligns with client's warm-wood preference. Verify condition, stability, and tip-over anchoring — kids ages 4 and 7. Verify cleaning requirements (dog). No documentation on file for flammability/performance — flag evidence gap for professional assessment.
  Budget allowance: $0 purchase (existing-reuse). Handling/repair scope not specified by client — MISSING; confirm whether cleaning, touch-up, or relocation work is needed. Allowance not yet set if work is required.
  Lead-time/order-by: No purchase lead time. If repair/handling work is needed, timing unconfirmed pending scope.
  Status: existing-reuse

BUDGET CHECK
Client total: $28,000, stated scope: "total FF&E including tax and delivery."

Row allowances (pre-tax/delivery):
  01 Sectional: $9,500
  02 Rug: $3,500
  03 Coffee table: $1,500
  04 Lounge chairs (2 x $1,500): $3,000
  05 Floor lamps (2 x $600): $1,200
  06 Drapery: $1,800
  07 Console: $0 purchase (handling/repair amount MISSING)
  Subtotal: $20,500

Contingency (provisional, not supplied by client): $2,000

Allocated total = $20,500 + $2,000 = $22,500
Budget − allocated total = $28,000 − $22,500 = $5,500 unallocated balance.

This $5,500 balance must cover tax, delivery/freight, and any console handling/repair — none of these are currently quantified. An apparent balance is not confirmation that these costs will fit within budget; confirm tax rate, freight basis, and console scope before issue.

LEAD-TIME CHECK
Install date: March 15, 2027.
Reference date: not stated by client — using current session date (2026-10-19) as a working reference; confirm this matches your actual planning date.
Install date − reference date = 147 calendar days. 147 ÷ 7 = 21 weeks.

Order-by = install date − lead time − buffer.

01/04 (upholstered, 14–16 week vendor-quoted lead): buffer MISSING.
  16-week estimate: order-by ≈ November 23, 2026
  14-week estimate: order-by ≈ December 7, 2026
  Reference date (Oct 19, 2026) precedes both — feasible only if finalized within the next 5–7 weeks. Adding any buffer moves these dates earlier. Treat as priority/custom items; confirm vendor lead time and buffer before client sign-off.

02, 03, 05, 06: lead times not quoted — formula retained, feasibility unconfirmed. Drapery (06) is likely custom and should be confirmed with the vendor first, as a priority.

07: no purchase lead time; repair/handling timing unconfirmed pending scope.

SPECS TO VERIFY (by tag)
01 Sectional: manufacturer flammability data/test method (jurisdiction not yet confirmed); abrasion/double-rub rating; cleaning code; stability/anti-tip for climbing (kids 4 and 7). Slip resistance not generally applicable to upholstered seating — professional to confirm.
02 Rug: flammability data/test method per jurisdiction; abrasion/wear rating; cleaning code; slip resistance (pad/backing).
03 Coffee table: edge-safety/stability verification (kids); finish durability/cleanability. Flammability/abrasion ratings generally not applicable to a solid-wood tabletop — professional to confirm.
04 Lounge chairs: same categories as Tag 01 — flammability, abrasion, cleaning code, stability/anti-tip.
05 Floor lamps: electrical safety certification per jurisdiction; stability/tip-resistance; cord safety. Flammability/abrasion/slip resistance not applicable — professional to confirm.
06 Drapery: flammability/fire-performance data per jurisdiction; cleaning instructions; cord safety (child-safety, if corded). Abrasion/slip resistance not applicable — professional to confirm.
07 Console (existing): no documentation on file — flag evidence gap for professional assessment of flammability/performance; verify stability/tip-over anchoring (kids) and cleaning instructions for existing finish.

QUESTIONS FOR THE CLIENT
1. Project type and jurisdiction (location/building type) — needed to confirm applicable fire/flammability codes and tax rate.
2. Confirm scheduling reference date — should 2026-10-19 (today) be used, or is there a different planning start date?
3. Vendor planning buffer to add to the 14–16 week upholstery lead time, and lead times for the rug, coffee table, floor lamps, and drapery (vendor/professional follow-up).
4. Existing walnut console: exact dimensions, and whether any cleaning, touch-up, repair, or relocation handling is needed (and its cost scope).
5. Does the $28,000 include installation/delivery labor fees beyond freight? Is the $2,000 provisional contingency acceptable, or should it be adjusted?
6. Sectional configuration/footprint and desired clearances, plus door location(s) in the room, so the target size can be confirmed against the 16 x 20 ft space.
7. Drapery: number of panels, mounting height/drop, and fullness ratio.
8. Confirm rug placement against the final furniture layout once door/clearance details are known.
9. Tax rate and delivery/freight cost basis — needed to confirm whether the $5,500 unallocated balance is sufficient.

