# Transcript — law-en-research-memo-01 — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:27:31+00:00
- duration_s: 74.4
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

Preliminary research framework — Sample Bakery LLC v. R. Example (Illinois state court)

Everything below is a starting map, not advice. Every point must be verified in primary sources by a licensed Illinois attorney before it is relied on or communicated to the client.


1. LEGAL ISSUES (framed as questions)

  A. Is the 2022 non-compete enforceable at all under Illinois' statutory regime for restrictive covenants that took effect in 2022? [AUTHORITY TO FIND]
     - Does R. Example's compensation fall below the statutory earnings threshold that makes a non-compete void regardless of its terms?
     - Were the statutory procedural prerequisites met (written advice to consult counsel, minimum review period before signing)?
     - Was the covenant supported by "adequate consideration" as the statute defines it?

  B. If the covenant survives the statute, is it enforceable under Illinois common law reasonableness analysis? [AUTHORITY TO FIND]
     - Does the bakery have a legitimate business interest worthy of protection?
     - Are the 2-year duration, 100-mile radius, and "any baked-goods sales" scope no broader than necessary?
     - Is the covenant unduly burdensome on the employee or injurious to the public?

  C. If the covenant is overbroad, will an Illinois court modify ("blue-pencil"/reform) it rather than strike it, and what factors govern that discretion? [AUTHORITY TO FIND]

  D. Independent of the non-compete, does the bakery have a claim based on R. Example's solicitation of its café customers?
     - Is there a separate customer non-solicitation clause, and does it face the same statutory hurdles (the statute treats non-solicits differently, with its own threshold)? [AUTHORITY TO FIND]
     - Misappropriation of trade secrets (customer lists, pricing, volumes) under Illinois' trade secrets statute? [AUTHORITY TO FIND]
     - Tortious interference with business relationships or prospective economic advantage?
     - Breach of fiduciary duty / duty of loyalty for conduct while still employed (if any)?

  E. Can the bakery obtain a temporary restraining order or preliminary injunction, and what must it show? [AUTHORITY TO FIND]

  F. Exposure: if the bakery sues and loses, is it liable for R. Example's attorney fees under the statute's fee-shifting provision? [AUTHORITY TO FIND] Any risk of a counterclaim?

  G. Choice-of-law / forum-selection clauses in the agreement, if any, and whether they are honored. [AUTHORITY TO FIND]


2. ELEMENTS / FACTORS (as generally understood; all to be confirmed)

  A. Statutory enforceability (Illinois restrictive-covenant statute, effective 2022)
     - Employee's actual or expected annualized earnings exceed the statutory floor for non-competes (the floor was set in the $70,000s at enactment and escalates over time). At $48,000 base, the client is likely below it unless commissions/bonuses push total earnings over. If below, the covenant is void. [AUTHORITY TO FIND — exact threshold and definition of "earnings"]
     - Separate, lower earnings threshold applies to customer non-solicitation covenants. [AUTHORITY TO FIND]
     - Employer advised the employee in writing to consult an attorney before signing. [AUTHORITY TO FIND]
     - Employee was given the statutory minimum number of days to review before signing (or knowingly waived). [AUTHORITY TO FIND]
     - Adequate consideration: either a defined minimum period of continued employment after signing, or other professional/financial benefits sufficient on their own. R. Example worked roughly four years, which likely satisfies the continued-employment route, but confirm start date and signing date. [AUTHORITY TO FIND]
     - Covenant is ancillary to a valid employment relationship.
     - Legitimate business interest exists (statute codifies the totality-of-circumstances test). [AUTHORITY TO FIND]

  B. Common-law reasonableness (Illinois three-part test)
     - No greater than required to protect a legitimate business interest (near-permanent customer relationships, confidential information, time/place/scope considered together).
     - No undue hardship on the employee.
     - Not injurious to the public.
     Red flags on these facts: 100-mile radius for a wholesale bakery whose café customers may be concentrated locally; "any baked-goods sales" bars work for any competitor in any role; 2 years is at the long end for a sales employee.

  C. Judicial reformation
     - Statute permits courts to reform or sever rather than void, but lists factors (fairness, good-faith drafting, extent of overbreadth) and signals that courts may refuse to rewrite covenants that were badly overbroad as written. [AUTHORITY TO FIND]

  D. Trade secret misappropriation
     - Information qualifies as a trade secret (sufficiently secret to derive economic value; reasonable efforts to maintain secrecy).
     - Misappropriation by improper acquisition, use, or disclosure.
     - Customer identities are often not protectable when readily ascertainable (cafés are public businesses); pricing, margins, volume, and contract terms are stronger candidates.

  D-2. Tortious interference with prospective economic advantage
     - Reasonable expectancy of a valid business relationship.
     - Defendant's knowledge of it.
     - Purposeful interference preventing the expectancy from ripening.
     - Damages.
     - Competitor's privilege defense: lawful competition is generally protected absent wrongful means.

  E. Preliminary injunction (Illinois)
     - Clearly ascertainable right in need of protection.
     - Irreparable harm without the injunction.
     - No adequate remedy at law.
     - Likelihood of success on the merits.
     - Balance of hardships (often considered). [AUTHORITY TO FIND]

  F. Fee exposure
     - Statute awards reasonable attorney fees to an employee who prevails against an employer's enforcement action. [AUTHORITY TO FIND]


3. FACTS STILL NEEDED FROM THE CLIENT

  - Full copy of the signed agreement; exact signing date (before or after the statute's effective date matters); any amendments.
  - R. Example's total compensation: base, commissions, bonuses, benefits — by year, and expected annualized figure at signing and at departure.
  - Start date and separation date; whether he signed on day one or after starting.
  - Whether he was given written advice to consult counsel and how many days he had the document before signing; any waiver.
  - Any separate confidentiality clause, customer non-solicitation clause, choice-of-law, forum, fee-shifting, or tolling provisions.
  - What he actually had access to: customer lists, pricing sheets, contract terms, margins, recipes/formulas, supplier terms. How was that information protected (passwords, NDAs, labeled confidential)?
  - Evidence of what he took or is using: emails forwarded to personal accounts, downloads, devices not returned, specific customers contacted, what he said to them.
  - Which customers he has contacted; whether any have switched or reduced orders; dollar value; whether those relationships were developed by him or pre-existed him.
  - Geography: where the client's customers actually are; where the competitor is; whether 100 miles bears any relation to the client's real market.
  - Any conduct while still employed (solicitation before resigning, diverting orders).
  - Whether the client sent a cease-and-desist letter or has communicated with the competitor; whether the competitor knows of the covenant (relevant to interference claim against the competitor).
  - Client's goals and budget: injunction, damages, or just a deterrent letter; tolerance for fee-shifting risk.
  - Any prior enforcement of this form agreement against other employees; whether other employees signed the same form (consistency and good-faith drafting).


4. RESEARCH PLAN

  Primary sources to pull
  - Illinois statute governing employee non-compete and non-solicitation covenants (enacted 2021, effective 2022): full text, including definitions of "earnings," thresholds and escalation schedule, consideration definition, notice/review requirements, reformation provision, fee-shifting. [AUTHORITY TO FIND]
  - Illinois trade secrets statute: definitions, remedies, injunction provision. [AUTHORITY TO FIND]
  - Illinois civil procedure provisions on TROs and preliminary injunctions. [AUTHORITY TO FIND]
  - Illinois Supreme Court and Appellate Court decisions on: legitimate business interest totality test; adequate consideration for post-hire or at-hire covenants; blue-penciling discretion; customer-list trade-secret status; competitor's privilege in interference claims. Prioritize the First District (Cook County) and whatever district the venue falls in. [AUTHORITY TO FIND]
  - Post-2022 appellate or circuit court decisions applying the new statute — the body of case law is still thin, so check for the most recent opinions and any trial-court orders on Westlaw/Lexis.
  - Illinois Attorney General guidance or enforcement actions concerning low-wage non-competes.
  - Secondary for orientation only (not citable): Illinois practice treatises on restrictive covenants; IICLE chapters; bar journal articles on the 2022 statute.

  Databases
  - Westlaw or Lexis: Illinois state cases, statutes annotated, trial court orders; KeyCite/Shepardize everything.
  - Illinois General Assembly website for official statutory text and legislative history (public acts, bill synopsis).
  - Illinois Courts website for opinions not yet in commercial databases.
  - Cook County (or relevant county) Clerk electronic docket for recent non-compete injunction filings and rulings.
  - Fastcase / Google Scholar as a cross-check only.

  Suggested search terms and queries
  - "non-compete" OR "noncompete" OR "covenant not to compete" /s Illinois /s ("earnings threshold" OR "void" OR "low-wage")
  - "adequate consideration" /p "restrictive covenant" /p (two years OR "continued employment") Illinois
  - "legitimate business interest" /p "totality of the circumstances" /p "restrictive covenant"
  - "near-permanent" /s customer /s relationship /s Illinois
  - "blue pencil" OR "judicial reformation" OR "reform" /p "restrictive covenant" Illinois
  - "customer list" /p "trade secret" /p ("readily ascertainable" OR "reasonable efforts") Illinois
  - "tortious interference" /p "prospective economic advantage" /p "competitor's privilege" Illinois
  - "preliminary injunction" /p "non-compete" OR "noncompete" /p Illinois /p ("irreparable harm" OR "ascertainable right")
  - "attorney's fees" /p employee /p prevail /p "restrictive covenant" Illinois (statutory fee-shifting)
  - "advise in writing" OR "consult with an attorney" /p "14" OR "fourteen" /p "restrictive covenant" (verify the actual review-period number in the statute)
  - "sales" OR "salesperson" /p "non-compete" /p ("100 miles" OR "radius" OR "geographic") Illinois /p (bakery OR food OR wholesale OR distributor)
  - Filter all case searches to decisions after January 1, 2022 first, then expand to pre-statute common law for reasonableness factors still relevant.

  Sequencing
  1. Statute first: if the earnings threshold or notice requirements are not met, the non-compete analysis may end there and the client's realistic path shifts to trade-secret, non-solicit (if present and above its own threshold), and interference theories.
  2. Then the agreement's other clauses.
  3. Then common-law reasonableness and reformation, only if the covenant clears the statute.
  4. Then injunction standard and fee-exposure analysis to inform a go/no-go recommendation.

Again: nothing above should be relied on until each proposition is confirmed against the current statutory text and controlling Illinois decisions by a licensed Illinois attorney.

