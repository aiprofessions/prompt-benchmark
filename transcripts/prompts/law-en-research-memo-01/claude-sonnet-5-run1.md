# Transcript — law-en-research-memo-01 — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:40:39+00:00
- duration_s: 52.5
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

LEGAL RESEARCH FRAMEWORK — Sample Bakery LLC / Former Employee Non-Compete

Disclaimer: This is a preliminary issue-spotting outline only. Every legal standard, element, threshold, and authority referenced below must be independently verified in primary Illinois sources by a licensed attorney before any advice is given to the client or any action is taken.

1. LEGAL ISSUES (as questions)

A. Is the 2022 non-compete agreement enforceable under Illinois law given R. Example's compensation level at signing?

B. Even if facially valid, are the agreement's restrictions (2-year duration, 100-mile radius, "any baked-goods sales" scope) reasonable in time, geography, and activity under Illinois's reasonableness test?

C. Was there adequate consideration for the covenant (e.g., sufficient continued employment period after signing, or other consideration), independent of salary?

D. Does the agreement function more as a non-solicitation covenant (restricting solicitation of client's customers) than a true non-compete, and if so, does a different enforceability standard or statutory threshold apply?

E. Did the agreement comply with Illinois statutory procedural requirements for post-2022 non-competes (e.g., advance notice/review period, advisement to consult counsel) at the time of signing?

F. Is there a legitimate, protectable business interest (near-permanent customer relationships, confidential pricing/customer data, trade secrets) supporting the restriction, separate from mere competition?

G. Has R. Example engaged in actual breach (competing within radius, soliciting former customers) sufficient to trigger relief?

H. Is there an independent tortious interference with business relationships/contract claim against R. Example or his new employer?

I. Is there misappropriation of trade secrets or confidential information (customer lists, pricing, margins) under Illinois trade secrets law?

J. What remedies are available — preliminary/permanent injunction, damages, liquidated damages (if any clause exists), attorney's fees — and can an overbroad covenant be reformed ("blue-penciled") by a court rather than voided entirely?

K. Does the agreement specify governing law, forum, or arbitration that affects where/how Sample Bakery must proceed?

2. ELEMENTS / FACTORS TO ESTABLISH (as generally understood — verify each in primary sources)

Issue A/C — Validity of covenant:
 - Existence of valid contract (offer, acceptance, consideration)
 - Adequate consideration: continued at-will employment for a substantial period after signing (Illinois case law has used a general guideline, often cited around two years of continued employment, absent other consideration — [AUTHORITY TO FIND]), or other consideration (signing bonus, raise, access to trade secrets) given at or near execution
 - Whether the employee met any statutory minimum earnings threshold for non-compete enforceability at the time the covenant was entered ([AUTHORITY TO FIND] — Illinois statutory earnings floor for non-competes, and a separate, lower floor for non-solicitation covenants) — $48,000 base salary should be checked against both thresholds as they stood in 2022 when signed, including any annual adjustment mechanism
 - Statutory procedural prerequisites: required advance notice before start of employment and/or express advisement to consult an attorney before signing ([AUTHORITY TO FIND])
 - Whether the statute in question applies at all (effective date, whether it is retroactive or applies only to agreements entered into after a certain date — need exact 2022 effective date and whether it covers a hiring that occurred during that year)

Issue B — Reasonableness (the three-part test generally used in Illinois):
 - Legitimate business interest (near-permanent customer relationships, confidential information, trade secrets, goodwill)
 - Reasonable temporal scope relative to the interest protected
 - Reasonable geographic scope relative to where the employee actually worked/had customer contact
 - Reasonable scope of activity restricted (not broader than necessary to protect the interest)
 - No undue hardship on the employee
 - Not injurious to the public

Issue F — Legitimate business interest factors (totality-of-circumstances, generally):
 - Near-permanent nature of customer relationships
 - Employee's acquisition of confidential information through employment
 - Time and expense invested by employer in developing customer relationships
 - Degree of customer contact and employee's role in cultivating goodwill
 - Restrictions on employee's post-employment competitive activities actually tied to protecting that interest

Issue H — Tortious interference (generally elements needed):
 - Valid business relationship or expectancy with identifiable customers
 - Defendant's knowledge of the relationship
 - Intentional and unjustified interference inducing breach or termination
 - Resulting damages

Issue I — Trade secret misappropriation (generally):
 - Existence of a trade secret (customer lists, pricing, margins — must be secret, have economic value from secrecy, subject to reasonable protection measures)
 - Misappropriation (improper acquisition, use, or disclosure)
 - Damages or unjust enrichment

Issue J — Remedies:
 - Irreparable harm, likelihood of success on merits, balance of hardships, public interest (preliminary injunction standard — [AUTHORITY TO FIND] exact Illinois formulation)
 - Availability of blue-penciling/reformation versus outright invalidation of overbroad provisions ([AUTHORITY TO FIND] — Illinois courts' willingness to reform vs. void)
 - Contractual liquidated damages clause (if present) and its enforceability
 - Fee-shifting clause (if present)

3. FACTS STILL NEEDED FROM THE CLIENT

 - Full copy of the signed agreement (exact language of restrictive covenants, any severability/reformation clause, choice-of-law/forum/arbitration clause, liquidated damages clause, confidentiality clause)
 - Exact date of hire vs. exact date agreement was signed (same day? before start? after start?) — critical for consideration and notice-period analysis
 - Whether employee was given advance written notice of the agreement before accepting the job offer, and whether he was advised in writing to consult an attorney, and how much time he had to review before signing
 - Employee's full compensation history 2022–2026 (base salary, bonuses, commissions) — need total "earnings" as Illinois statute may define it, not just base salary, and need any changes since hire
 - Employee's actual job duties and level of customer contact (was he primarily a salesperson with direct customer relationships, or more limited role?)
 - Whether employee had access to confidential pricing, margin, or recipe/formula information, and what protective measures (NDAs, access controls, marked confidential) were in place
 - Specific customers he is now contacting — are these customers he personally serviced/developed, or ones he never had contact with at Sample Bakery?
 - Whether the new employer is within the 100-mile radius as measured from client's location, and the correct measurement point under the contract's language
 - Nature and extent of actual or threatened harm: lost accounts, lost revenue, specific dollar impact
 - Whether Sample Bakery has evidence of active solicitation (emails, texts, orders diverted) versus mere incidental competition
 - Whether there is a separate NDA, confidentiality agreement, or trade-secret policy signed by employee
 - Whether other employees have signed similar agreements and whether company has a practice of enforcing them (relevant to estoppel/waiver arguments)
 - Any prior resignations/non-compete enforcement history for the company
 - Whether the new employer was aware of the non-compete when hiring R. Example (relevant to tortious interference)
 - Company's registered location(s) and whether multiple bakery locations affect the 100-mile radius calculation
 - Illinois county/venue where company is based, for forum considerations

4. RESEARCH PLAN

Primary sources to search:
 - Illinois compiled statutes — specifically provisions governing restrictive covenants in employment (freedom-to-work type legislation), including earnings thresholds, notice periods, and effective dates/amendments — [AUTHORITY TO FIND exact statutory citation and current text]
 - Illinois trade secrets statute (version of the uniform trade secrets act as adopted in Illinois) — [AUTHORITY TO FIND]
 - Illinois state appellate and supreme court decisions addressing: (a) the three-part reasonableness test for restrictive covenants, (b) adequate consideration/duration-of-employment rule, (c) legitimate business interest factors (totality of circumstances), (d) blue-penciling/reformation standards, (e) preliminary injunction standard in restrictive covenant cases, (f) tortious interference with business relationships elements — [AUTHORITY TO FIND for each]
 - Illinois pattern jury instructions, if applicable, for tortious interference and trade secret claims
 - Local circuit court rules for the county where suit would be filed (injunction motion procedures, TRO practice)

Databases:
 - Westlaw or Lexis: Illinois statutes annotated, Illinois case law (state courts), secondary sources (Illinois practice treatises on employment/restrictive covenants)
 - Illinois General Assembly official website for current statutory text and legislative history/effective dates
 - Illinois courts' official case search / CourtListener / Illinois Supreme and Appellate Court opinion archives for free verification
 - Bloomberg Law or Fastcase as alternative if available
 - Trade secret-specific treatises (e.g., Milgrim or similar) cross-referenced against Illinois adoption

Suggested search terms:
 - "Illinois" "restrictive covenant" "reasonableness" "legitimate business interest"
 - "Illinois" "non-compete" "earnings threshold" "Freedom to Work" OR "employee" "minimum compensation"
 - "Illinois" "non-solicitation" "customer" covenant threshold compensation
 - "Illinois" "adequate consideration" non-compete "continued employment" two years
 - "Illinois" "advance notice" non-compete "fourteen days" OR "review period" attorney advisement
 - "Illinois" "blue pencil" OR "reformation" restrictive covenant overbroad
 - "Illinois" preliminary injunction "irreparable harm" non-compete employee
 - "Illinois" tortious interference business expectancy employee solicitation
 - "Illinois" trade secret customer list pricing misappropriation employee
 - "Illinois" non-compete geographic scope "100 mile" OR radius reasonableness sales employee
 - "Illinois" non-compete duration "two years" bakery OR wholesale sales reasonableness

Next step: counsel should pull and read the current, verified text of the applicable Illinois statute on restrictive covenants (including any amendments and effective-date provisions covering a 2022-signed agreement), confirm whether base salary or total compensation controls the earnings threshold, and then shepardize/keycite the controlling Illinois appellate/supreme court authority on each element above before advising the client on enforceability or pursuing injunctive relief.

