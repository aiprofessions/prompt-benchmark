# Transcript — law-en-research-memo-01 — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:44:32+00:00
- duration_s: 67.0
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

NON-COMPETE / CUSTOMER SOLICITATION MEMO — Sample Bakery LLC v. R. Example
Preliminary issue-spotting only. Every point below must be verified in primary sources by a licensed Illinois attorney before being relied on or communicated to the client.

1. LEGAL ISSUES (framed as questions)

  1.1 Is the 2022 non-compete enforceable at all under Illinois's restrictive-covenant statute, given that the employee's earnings ($48,000 base) appear to fall below the statutory earnings threshold for non-competes? [AUTHORITY TO FIND]

  1.2 If the agreement contains (or can be read as) a customer non-solicitation covenant rather than a pure non-compete, does it survive under the separate, lower earnings threshold that Illinois applies to non-solicits? [AUTHORITY TO FIND]

  1.3 Was the covenant supported by adequate consideration under Illinois law, where it was signed at hiring and the employee stayed roughly four years? [AUTHORITY TO FIND]

  1.4 Did the employer satisfy Illinois's procedural prerequisites (written advice to consult counsel, minimum review period before signing)? [AUTHORITY TO FIND]

  1.5 Is the covenant reasonable in scope — 2 years, 100 miles, "any baked-goods sales" — and does it protect a legitimate business interest? [AUTHORITY TO FIND]

  1.6 If overbroad, will an Illinois court blue-pencil / judicially reform it rather than void it, and what does the agreement itself say about modification? [AUTHORITY TO FIND]

  1.7 Can the client obtain a temporary restraining order or preliminary injunction, and what showing is required? [AUTHORITY TO FIND]

  1.8 Independent of the covenant: does the client have claims for trade-secret misappropriation (customer list / pricing), breach of fiduciary duty or duty of loyalty (pre-resignation conduct), or tortious interference against Example and/or the new employer? [AUTHORITY TO FIND]

  1.9 Fee-shifting exposure: does Illinois law allow a prevailing employee to recover attorney's fees in an unsuccessful enforcement action, and what does the contract say about fees? [AUTHORITY TO FIND]

  1.10 Are there federal overlays (any FTC rule status as of 2026; any applicable federal trade-secret statute) and does the agreement contain a choice-of-law or forum clause? [AUTHORITY TO FIND]

2. ELEMENTS / FACTORS FOR EACH ISSUE (as generally understood — verify)

  2.1 Statutory threshold (non-compete)
    - Covenant falls within the statutory definition of "covenant not to compete"
    - Employee's "earnings" (as statutorily defined — may include bonuses, commissions, etc.) met or exceeded the threshold in effect at signing / enforcement
    - Agreement entered on or after the statute's effective date (critical: "2022" is ambiguous — see Part 3)
    - Consequence if below threshold: covenant void and unenforceable, not merely voidable

  2.2 Statutory threshold (non-solicit)
    - Covenant falls within the statutory definition of "covenant not to solicit"
    - Employee's earnings met the (lower) non-solicit threshold
    - Whether the agreement's language can be severed/read to contain a standalone non-solicit

  2.3 Adequate consideration
    - Continued employment for the judicially recognized minimum period, OR
    - Independent professional or financial benefit (signing bonus, raise, equity, etc.) tied to the covenant
    - Statutory codification of the consideration standard [AUTHORITY TO FIND]

  2.4 Procedural prerequisites
    - Employee advised in writing to consult an attorney
    - Employee given the statutory minimum number of days to review before signing (or waived it)
    - Covenant in writing, signed

  2.5 Reasonableness / legitimate business interest
    - Covenant no greater than required to protect a legitimate business interest
    - No undue hardship on employee
    - Not injurious to the public
    - Legitimate business interest assessed on totality of circumstances: near-permanent customer relationships, employee's acquisition of confidential information through employment, time and place restrictions, activity restrictions
    - Reasonableness of each dimension: duration (2 yrs), geography (100 mi), activity scope ("any baked-goods sales" — likely broader than the employee's wholesale/café role)

  2.6 Judicial reformation
    - Statutory factors a court may consider in deciding whether to reform (fairness of restraint as written, good-faith effort to protect legitimate interest, extent of reformation needed)
    - Severability / modification clause in the agreement
    - Court's discretion to refuse reformation of a drastically overbroad covenant

  2.7 Injunctive relief (TRO / preliminary injunction)
    - Clearly ascertainable right needing protection
    - Irreparable harm absent injunction
    - No adequate remedy at law
    - Likelihood of success on the merits
    - Balance of hardships
    - Bond requirement [AUTHORITY TO FIND]

  2.8 Alternative claims
    Trade secrets: information qualifies as a trade secret (economic value from secrecy, reasonable secrecy measures); misappropriation (improper acquisition, use, or disclosure); damages or threatened misappropriation for injunctive relief
    Fiduciary duty / loyalty: employee solicited customers or coworkers or diverted opportunities before resigning; use of employer resources to prepare to compete
    Tortious interference (against new employer or Example): valid contract / reasonable expectancy; defendant's knowledge; intentional and unjustified inducement of breach or interference; breach/loss; damages

  2.9 Fee-shifting
    - Statutory employee fee-recovery provision triggered where employer sues and loses
    - Contractual fee clause (mutual or one-way)

3. FACTS STILL NEEDED FROM THE CLIENT

  Agreement
    - Full signed copy, with exact date of signature and start date (before or after January 1, 2022 is decisive) [AUTHORITY TO FIND]
    - Exact covenant language: non-compete only, or separate non-solicit, confidentiality, and non-disparagement provisions
    - Choice-of-law, forum, severability/reformation, fee, tolling, and liquidated-damages clauses
    - Whether the employee was told in writing to consult counsel and how many days elapsed between receiving the agreement and signing
    - Any later agreements, amendments, handbooks, or confidentiality acknowledgments

  Compensation
    - Total earnings each year 2022–2026: base, commissions, bonuses, overtime, benefits
    - Was any consideration given specifically for the covenant (signing bonus, raise, stock)?
    - Any raise that pushed earnings above a threshold in a later year

  Employment facts
    - Job duties; which customers he was assigned to or developed; whether he brought customers with him
    - Access to pricing, margins, recipes, supplier terms, customer lists; what secrecy measures the client used (password protection, NDAs, need-to-know access)
    - Did he take or forward documents / data on departure? Device and email audit status
    - Exit interview notes; did he receive a departure reminder of his obligations?

  Post-departure conduct
    - Names of customers contacted; how the client learned of it; any lost accounts and dollar value
    - Evidence of solicitation vs. customers approaching him
    - Any evidence of pre-resignation solicitation or competitor coordination
    - Identity of the competitor; whether it knew of the covenant (relevant to tortious interference and a cease-and-desist to the competitor)

  Business / strategy
    - Client's actual market radius (does it serve customers 100 miles out?) — bears on reasonableness
    - Client's appetite for litigation cost, fee-shifting risk, and a possible counterclaim
    - Whether the client has sent any demand letter yet
    - Any prior enforcement of this form against other employees

4. RESEARCH PLAN

  Primary sources to locate (all [AUTHORITY TO FIND])
    - Illinois statute governing employee non-compete and non-solicit covenants, including: definitions, earnings thresholds (and any inflation adjustments scheduled for 2027 and beyond), effective date, consideration rule, attorney-review notice period, legitimate-business-interest factors, reformation factors, employee fee-shifting
    - Illinois Supreme Court decision(s) establishing the totality-of-circumstances legitimate-business-interest test
    - Illinois appellate decisions on adequate consideration / continued-employment duration
    - Illinois Trade Secrets Act and federal trade-secret statute
    - Illinois rules and case law on TRO / preliminary injunction standards and bond
    - Illinois case law on employee duty of loyalty and tortious interference with contract / prospective advantage
    - Current status of any federal non-compete rule and the Illinois Attorney General's enforcement posture
    - Any 2024–2026 Illinois amendments (e.g., carve-outs for specific industries; construction, healthcare, veterans — confirm none apply)

  Databases
    - Westlaw / Lexis: Illinois Compiled Statutes (annotated), Illinois Supreme Court and Appellate Court reports, N.D. Ill. decisions applying Illinois law
    - Illinois General Assembly website (ilga.gov) for current statutory text and Public Acts amending the restrictive-covenant statute
    - Illinois Supreme Court and Appellate Court opinion archives (illinoiscourts.gov)
    - Illinois Attorney General site for workplace-rights / non-compete guidance
    - Illinois State Bar Association and IICLE practice materials as secondary orientation only
    - Secondary: Illinois Law and Practice / IICLE "Employment Law" chapters on restrictive covenants; law-review and bar-journal commentary on the statutory thresholds

  Suggested search terms / strings
    - "freedom to work" /s "covenant not to compete" /s earnings
    - "covenant not to solicit" /s threshold /s $45,000 OR $75,000 (confirm current figures in the statute itself)
    - "adequate consideration" /s "continued employment" /s "two years" /s restrictive covenant
    - "legitimate business interest" /s "totality of the circumstances" /s non-compete /s Illinois
    - "judicial reformation" OR "blue pencil" /s "covenant not to compete" /s Illinois
    - "preliminary injunction" /s non-compete /s "irreparable harm" /s Illinois /s customer
    - "customer list" /s "trade secret" /s "reasonable measures" /s Illinois
    - "duty of loyalty" /s solicit /s "prior to resignation" /s Illinois
    - "tortious interference" /s "new employer" /s non-compete /s Illinois
    - "attorney's fees" /s employee /s "covenant not to compete" /s prevail
    - Filters: jurisdiction = Illinois; date = 2022–present for statutory interpretation; keep pre-2022 Illinois Supreme Court authority on consideration and legitimate business interest

  Suggested sequence
    1. Pull statute text and effective-date provision first — if the agreement post-dates the statute and earnings are below threshold, the non-compete is likely dead and research shifts to issues 1.2 and 1.8.
    2. Pull the agreement and payroll records from the client before investing in reasonableness research.
    3. Assess trade-secret / loyalty claims as the fallback path to injunctive relief.
    4. Evaluate fee-shifting exposure before recommending suit; consider a cease-and-desist to the competitor as a lower-risk first step.

Reminder: nothing above is legal advice or a statement of current law. Every proposition, threshold figure, time period, and element must be confirmed against primary Illinois and federal sources by a licensed attorney before use.

