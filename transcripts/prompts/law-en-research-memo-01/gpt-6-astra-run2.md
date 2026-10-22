# Transcript — law-en-research-memo-01 — gpt-6-astra — run 2

- model_id: `gpt-6-astra` (provider `openai`)
- started_utc: 2026-10-19T11:55:43+00:00
- duration_s: 78.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: dc4abdb0c63d00c579093230345e61dec8ac0d18e390129631dbcb1cff1166e3

## Query (verbatim, from query file)

```text
You assist a US litigation associate at the start of legal research.
From the facts below produce: (1) the legal issues, framed as questions; (2) for each issue, the elements or factors the client would need to establish, as generally understood; (3) facts still needed from the client; (4) a research plan: which primary sources and databases to search and suggested search terms.
STRICT RULE: do not name any case, statute section or citation. Where authority is needed write [AUTHORITY TO FIND]. State that every point must be verified in primary sources by a licensed attorney.
Facts:
Jurisdiction: Illinois (state court).
Client: Sample Bakery LLC (fictional), a small wholesale bakery.
A former sales employee ("R. Example") signed a non-compete at hiring in 2022: 2 years, 100-mile radius, any baked-goods sales. Base salary was $48,000/year.
He resigned in August 2026 and now sells for a competing bakery 30 miles away, contacting the client's café customers.
The client wants to know whether it can stop him.
```

## Output (verbatim stdout, session metadata stripped)

Preliminary research outline—not a legal opinion. Every point below must be verified in primary sources by a licensed attorney. The stated facts do not yet establish that Sample Bakery LLC can stop R. Example from competing or contacting customers.

The first priority is enforceability at signing. The $48,000 base salary may fall below the Illinois earnings threshold applicable to a non-compete entered into in 2022. Confirm qualifying earnings rather than assuming base salary is the entire measure. If the agreement was prohibited when signed, evidence of competition alone would not cure that defect. [AUTHORITY TO FIND]

1. Legal issues and elements or factors

A. Was the non-compete legally eligible for enforcement when signed in 2022?

Questions:
  Did R. Example’s qualifying earnings exceed the applicable threshold? Which rules govern a 2022 agreement enforced after an August 2026 resignation?

Elements or factors to investigate:
  • Whether the worker, employer, and agreement fall within Illinois’s restrictions on employee non-competes.
  • The earnings threshold applicable at execution, how earnings are defined and calculated, and the treatment of commissions, bonuses, and benefits.
  • Whether any later amendment or re-execution affects the governing date.
  • Whether a later earnings increase could have any legal effect on an agreement impermissible at inception.
  • Any applicable exclusion or exception. [AUTHORITY TO FIND]

B. Were the agreement’s consideration and execution requirements satisfied?

Questions:
  Was there adequate consideration, and did the employer comply with required notice and review procedures?

Elements or factors to investigate:
  • Whether the employer advised R. Example in writing to consult an attorney.
  • Whether it supplied the agreement with the required advance notice or review opportunity; distinguish an employee’s voluntary early signing from denial of that opportunity.
  • Whether continued employment or other professional or financial benefits supplied adequate consideration. Employment from 2022 to 2026 may support this requirement, but would not independently cure other defects.
  • Assent, execution, and any contractual defenses. [AUTHORITY TO FIND]

C. Does the restriction reasonably protect a legitimate business interest?

Questions:
  Are two years, a 100-mile radius, and a ban on any baked-goods sales reasonably necessary, or are they broader than the client’s protectable interests?

Elements or factors to investigate:
  • A legitimate business interest assessed under the totality of the circumstances, including customer relationships, employee customer contact, and access to confidential information.
  • The relationship between the restriction and R. Example’s actual duties, customers, products, and territory.
  • Whether the duration corresponds to the time reasonably needed to protect customer goodwill or sensitive information.
  • Whether the geographic scope reflects the bakery’s actual market and the employee’s work.
  • Whether “any baked-goods sales” prohibits materially different roles or market segments.
  • Whether the restriction creates undue hardship or harms the public.
  • Whether the covenant is ancillary to a valid employment relationship. Preventing ordinary competition alone should not be assumed sufficient. [AUTHORITY TO FIND]

D. Has R. Example breached an enforceable restriction, and can a court narrow it?

Questions:
  Does his current conduct fall within the actual contract language? Could a court enforce a narrower restriction if the existing one is excessive?

Elements or factors to investigate:
  • A valid, enforceable agreement; the bakery’s required performance; prohibited conduct; and resulting injury, as required for the claim and requested remedy.
  • The contract’s geographic reference point: a competitor being 30 miles away does not necessarily establish where prohibited work occurs.
  • The triggering date, expiration date, covered activities, and any tolling language.
  • Any separate customer non-solicitation, non-dealing, or confidentiality covenant. Do not assume the non-compete contains one.
  • Rules governing judicial modification, including fairness, good faith, the extent of rewriting required, and contractual severability language.
  • Whether the identified defect is legally curable by narrowing; do not assume a court can rewrite around a threshold or execution defect. [AUTHORITY TO FIND]

E. Are there independent grounds to stop customer targeting or misuse of information?

Questions:
  Did R. Example misuse protected information, solicit customers before departure, or improperly interfere with customer relationships?

Elements or factors to investigate:
  • For trade-secret relief: specifically identifiable information, economic value from secrecy, reasonable secrecy measures, and acquisition, use, or disclosure through improper means or breach of a duty.
  • For confidentiality relief: a valid obligation and prohibited use or disclosure of covered information.
  • For pre-departure misconduct: an applicable duty of loyalty and conduct crossing the line from permissible preparation into disloyal competition.
  • For interference: an existing contract or sufficiently concrete business expectancy, knowledge, intentional and legally unjustified interference, causation, and loss; assess competition-based privileges or defenses.
  • Customer contact alone does not establish any of these claims. Distinguish public customer identities and general experience from protected pricing, margins, buying histories, and other nonpublic information. [AUTHORITY TO FIND]

F. Can the bakery obtain emergency or final injunctive relief, and what are the litigation risks?

Questions:
  Can it obtain a temporary restraining order, preliminary injunction, or permanent injunction? What relief would be appropriately limited?

Elements or factors to investigate:
  • A clearly ascertainable right needing protection.
  • Irreparable harm and inadequacy of a damages remedy.
  • A likelihood of success for preliminary relief, and the merits showing required for permanent relief.
  • Any applicable balancing of hardships and public-interest considerations.
  • Specific, ongoing or imminent harm—not merely the fact that a competitor hired the employee.
  • Promptness, notice, verified pleadings or supporting affidavits, security requirements, and special requirements for relief without notice.
  • Potential employee fee recovery, wrongful-injunction exposure, and other consequences of pursuing an unenforceable covenant. [AUTHORITY TO FIND]

2. Facts still needed from the client

Agreement and compensation:
  • Complete signed agreement, exhibits, amendments, offer letter, and related policies.
  • Exact hiring, delivery, signing, amendment, and resignation dates.
  • Written attorney-consultation advice and evidence of the review opportunity.
  • Compensation records showing salary, commissions, bonuses, and other potentially qualifying earnings at signing and afterward.
  • Any additional consideration, interruptions in employment, or material changes in role.
  • Choice-of-law, forum, severability, tolling, fee, and dispute-resolution provisions.

Business interests and scope:
  • Bakery locations, actual sales territory, delivery footprint, and customer distribution.
  • R. Example’s territory, accounts, duties, customer access, and specialized training.
  • Customer acquisition costs, relationship duration, ordering cycles, and how long sensitive pricing remains useful.
  • Whether café customers use multiple suppliers, have fixed-term contracts, or buy order by order.
  • Whether the bakery performed its own contractual obligations, including compensation.

Conduct and evidence:
  • New employer, job duties, work locations, and start date.
  • Which cafés he contacted, when, how, what he said, and whether contact was initiated by him or the customer.
  • Any solicitation or diversion while still employed.
  • Lost orders, reduced sales, cancellations, threatened departures, and customer statements linking losses to his conduct.
  • Downloads, exports, forwarded emails, device activity, retained documents, or use of nonpublic pricing.
  • Access controls, confidentiality policies, and other actual secrecy measures.
  • Date the bakery learned of the conduct, subsequent communications, and any delay in seeking relief.

Preserve relevant contracts, payroll records, communications, customer records, and access logs. Any review of personal accounts or devices should proceed only with lawful authority and attorney guidance.

3. Research plan

A. Start with official Illinois legislative materials

Sources:
  • Official Illinois General Assembly materials: current and historical enacted text, effective dates, amendments, and definitions governing restrictive covenants.
  • Official legislative materials governing trade secrets and available remedies.

Research tasks:
  • Identify the rules applicable to execution in 2022, rather than simply using the enforcement-year text.
  • Verify earnings thresholds, calculation methods, notice, consideration, modification, and fee provisions.

Suggested searches:
  “Illinois employee noncompete 2022 earnings threshold commissions”
  “Illinois noncompete earnings definition time agreement entered”
  “Illinois restrictive covenant attorney advice review period”
  “Illinois noncompete adequate consideration continued employment”
  “Illinois noncompete prevailing employee attorney fees”

All resulting propositions require [AUTHORITY TO FIND].

B. Search controlling and persuasive decisions

Sources:
  • Official Illinois Courts opinions.
  • Westlaw, Lexis, or Bloomberg Law for historical coverage, full-text searching, and citator review.
  • Use federal decisions applying Illinois law as supplemental persuasive material, not substitutes for controlling Illinois authority.

Research tasks:
  • Prioritize Illinois Supreme Court and relevant appellate district decisions.
  • Separate decisions applying the post-2022 framework from older common-law decisions.
  • Compare sales employees, wholesale distribution, customer relationships, broad product restrictions, and geographic limits.
  • Verify precedential status and subsequent treatment.

Suggested searches:
  “Illinois noncompete legitimate business interest totality customer relationships”
  “Illinois sales employee noncompete two years 100 miles”
  “Illinois noncompete any capacity product restriction undue hardship”
  “Illinois restrictive covenant judicial modification statutory invalidity”
  “Illinois customer solicitation ordinary competition confidential pricing”
  “Illinois employee duty loyalty solicitation before resignation”
  “Illinois interference business expectancy competitor privilege”

All resulting propositions require [AUTHORITY TO FIND].

C. Research injunction procedure and local practice

Sources:
  • Official Illinois procedural enactments and court rules.
  • The selected circuit court’s local rules and emergency-motion procedures.
  • Illinois appellate decisions on evidentiary requirements and injunction review.

Suggested searches:
  “Illinois temporary restraining order noncompete irreparable harm”
  “Illinois preliminary injunction customer goodwill adequate remedy”
  “Illinois injunction without notice verified complaint security”
  “Illinois restrictive covenant delay emergency relief”
  “Illinois wrongful injunction damages employee covenant”

All resulting propositions require [AUTHORITY TO FIND].

Recommended decision sequence: resolve earnings eligibility and execution requirements first, assess scope and evidence second, and evaluate emergency relief only after identifying an enforceable right and concrete threatened harm. Independently assess supported information-misuse or pre-departure misconduct claims even if the non-compete is invalid. [AUTHORITY TO FIND]

