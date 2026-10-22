# Transcript — law-en-research-memo-01 — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:55:24+00:00
- duration_s: 77.4
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

LEGAL RESEARCH FRAMEWORK — Sample Bakery LLC v. R. Example (Illinois, non-compete/customer solicitation)

Preliminary note: Everything below is a framework for initial research, not a legal conclusion. Every element, standard, and statutory reference must be verified against current Illinois primary authority by a licensed attorney before being relied on or asserted to a court. Where I have not named authority, I have marked it [AUTHORITY TO FIND].

====================================================================
1. LEGAL ISSUES (framed as questions)
====================================================================

A. Is the 2022 non-compete agreement enforceable under Illinois law as to R. Example, given his compensation level, the timing of signing relative to hire, and the scope of the restriction (2 years / 100 miles / any baked-goods sales)?

B. Does Illinois statutory law restricting or voiding non-competes for lower-wage employees apply to R. Example, based on his compensation at signing and/or at termination?

C. Did the employer satisfy any Illinois statutory notice/advisement requirements (e.g., advising the employee in writing to consult an attorney, and providing a minimum review period) before the agreement was signed in 2022?

D. Was there adequate consideration for the covenant under Illinois law (e.g., sufficient continued employment or other bargained-for consideration), given that it was apparently signed at hire?

E. Does the client have a protectable "legitimate business interest" (e.g., near-permanent customer relationships, confidential pricing/customer information, specialized training) sufficient to support the restriction, independent of the contract's literal terms?

F. Is the restriction's scope (temporal, geographic, and activity) reasonable as actually applied to this employee's role, or is it overbroad?

G. Has R. Example breached the agreement, and if so, what relief is available (injunction, damages, fees)?

H. Did R. Example or the competing bakery misappropriate trade secrets or confidential business information (customer lists, pricing, recipes/formulas) in violation of Illinois trade-secrets law?

I. Does the client have an independent claim for tortious interference with business relationships/contract against the competing bakery for recruiting R. Example or directing him to solicit the client's customers?

J. If litigation is pursued, is emergency/preliminary injunctive relief realistically available, and what is the likely timeline and evidentiary burden?

K. Does the agreement specify Illinois choice of law/forum, and is venue otherwise proper in Illinois state court?

====================================================================
2. ELEMENTS / FACTORS GENERALLY UNDERSTOOD FOR EACH ISSUE
====================================================================

(All subject to verification — standards below are generalized, not jurisdiction-confirmed language.)

A/F. Enforceability of restrictive covenant (reasonableness test)
   - Existence of a legitimate, protectable business interest
   - Reasonableness of temporal scope
   - Reasonableness of geographic scope
   - Reasonableness of scope of prohibited activity
   - Whether the restriction imposes undue hardship on the employee
   - Whether the restriction is injurious to the public
   - Totality-of-circumstances analysis (courts often weigh factors together rather than as a rigid checklist)
   - [AUTHORITY TO FIND] for exact Illinois formulation and any "blue-pencil"/severability doctrine allowing partial enforcement

B. Statutory compensation threshold restriction
   - Applicable minimum earnings threshold at the relevant time (may differ for agreements signed before vs. after a given statutory amendment)
   - Definition of "earnings" (base salary vs. total compensation, commissions, bonuses)
   - Whether the restriction at issue is a "non-compete" vs. a "non-solicitation" covenant (statute may treat these differently and set different thresholds)
   - Effective date of the statute and whether it applies retroactively to a 2022 agreement
   - [AUTHORITY TO FIND] exact threshold figures and statutory text in effect in 2022 and any amendments effective since

C. Statutory notice/advisement requirement
   - Whether employer advised employee in writing to consult an attorney before signing
   - Whether employee was given a minimum number of days to review before signing
   - Consequence of noncompliance (void vs. voidable vs. unenforceable covenant)
   - [AUTHORITY TO FIND] exact requirements, applicable employee categories, and remedy for noncompliance

D. Adequate consideration
   - Whether covenant was signed before or contemporaneous with start of employment (continued employment theory may not apply if signed at hire)
   - If signed at hire: whether initial employment itself can constitute sufficient consideration, or whether a minimum period of continued employment is additionally required under Illinois case law
   - Any additional consideration given (bonus, raise, training, access to confidential info)
   - [AUTHORITY TO FIND] current Illinois standard on continued-employment consideration and any minimum duration

E. Legitimate business interest (substantive, fact-based)
   - Near-permanent nature of customer relationships (how they were developed, length/duration, exclusivity, difficulty of acquisition)
   - Employee's acquisition of confidential information, trade secrets, or specialized training at employer's expense
   - Restrictive covenant's relationship to actual job duties and customer contact
   - [AUTHORITY TO FIND] Illinois factors for "near-permanence" and confidentiality prongs

G. Breach of contract
   - Valid, enforceable agreement
   - Performance by employer / excuse of conditions
   - Breach by employee (post-employment competitive conduct within restricted time/area/scope)
   - Resulting damages (or basis for equitable relief where damages are hard to quantify)

H. Trade secret / confidential information misappropriation
   - Existence of a trade secret (information deriving independent economic value from not being generally known; reasonable efforts to maintain secrecy)
   - Misappropriation (improper acquisition, use, or disclosure)
   - Causation and damages, or unjust enrichment, or basis for injunction
   - [AUTHORITY TO FIND] Illinois trade secrets statute definitions and remedies

I. Tortious interference with business relationship/contract
   - Existence of a valid business relationship or contractual expectancy
   - Third party's (competitor's) knowledge of the relationship/contract
   - Intentional and unjustified interference inducing breach or termination
   - Resulting damage to the client
   - [AUTHORITY TO FIND] Illinois elements for interference with contract vs. interference with prospective economic advantage (different standards may apply)

J. Preliminary/emergency injunctive relief
   - Likelihood of success on the merits
   - Irreparable harm without an injunction (and whether that harm is presumed or must be shown)
   - Balance of hardships between parties
   - Public interest considerations
   - Timeliness of the request (delay in seeking relief can undercut irreparable-harm argument)
   - [AUTHORITY TO FIND] Illinois state-court standard and any bond requirement

K. Choice of law / forum / venue
   - Governing law clause in the agreement (if any) and its enforceability
   - Proper venue under Illinois civil procedure rules based on residence/transaction location
   - [AUTHORITY TO FIND] whether any choice-of-law clause conflicts with the Illinois statute restricting non-competes (some statutes void out-of-state choice-of-law/forum clauses in certain circumstances)

====================================================================
3. FACTS STILL NEEDED FROM THE CLIENT
====================================================================

Timing/formation:
   - Exact hire date and exact date the non-compete was signed (before start, day one, or after some period of employment?)
   - Exact resignation date and last day of actual work
   - Whether employee received any written notice advising him to consult an attorney, and how many days he had to review the agreement before signing

Compensation:
   - Full compensation history: base salary at signing (confirm $48,000), any raises/bonuses/commissions over the employment, and total compensation at time of resignation (not just base salary — this affects any statutory threshold analysis)
   - Whether $48,000 was base-only or total annual compensation

Role and access:
   - His actual job title, duties, and whether "sales" is accurate — did he have exclusive or primary responsibility for specific customer accounts?
   - Did he have access to confidential pricing, margins, customer lists, recipes/formulas, or other proprietary information? What safeguards protected that information (passwords, confidentiality agreements, marked "confidential," limited access)?
   - Did the client provide him specialized training, certifications, or investment beyond ordinary job training?

Customer relationships:
   - Were the café customers he's now soliciting ones he personally developed, or pre-existing client-company relationships assigned to him?
   - How long has the client had relationships with those specific cafés, and how were those relationships originally formed (client's efforts vs. his personal efforts)?
   - Approximate revenue/profit the client derives from the customers he is now contacting

Departure and new employment:
   - Circumstances of resignation (voluntary resignation, termination, layoff — this matters because enforceability/equities can differ)
   - Exact identity and location of the new employer (confirm ~30 miles, within the 100-mile radius)
   - His specific role at the new employer — is he selling baked goods to the same or different customer types?
   - Evidence of actual solicitation: dates, communications, customers contacted, any resulting lost business or canceled orders

Agreement terms and documents:
   - Full copy of the signed non-compete/employment agreement, including any separate non-solicitation, confidentiality, or non-disclosure clauses
   - Severability/"blue-pencil" clause, choice-of-law clause, forum-selection clause, attorneys'-fees clause
   - Whether the agreement distinguishes "non-compete" from "non-solicitation of customers" (these may be analyzed and governed differently)

History/damages:
   - Whether the client has enforced (or attempted to enforce) similar covenants against other former employees, and outcome
   - Quantifiable harm to date: lost accounts, lost revenue, pricing undercutting, cancelled contracts
   - Any direct evidence the new employer directed, encouraged, or knew about the restrictive covenant when hiring him

====================================================================
4. RESEARCH PLAN
====================================================================

Primary sources to locate and read (before advising client):

   1. Illinois statute governing restrictive covenants for employees (the Illinois employee non-compete/freedom-to-work type statute) — confirm:
        - Earnings threshold(s) for non-competes and for non-solicitation covenants separately, and the effective date/version applicable to a 2022-signed agreement
        - Notice/advisement and review-period requirements
        - Remedies for noncompliance (void, voidable, severable, blue-pencil authority)
        - Any attorneys'-fee shifting provision for prevailing employee defendants
   2. Illinois trade secrets statute — definitions of trade secret, misappropriation, and remedies (injunction, damages, exemplary damages, fee-shifting)
   3. Illinois case law (Supreme Court and Appellate Court, all relevant districts) addressing:
        - The reasonableness test for non-competes (legitimate business interest factors, near-permanence of customer relationships, confidential information)
        - Adequate consideration standard where covenant signed at inception of at-will employment
        - Blue-penciling/partial enforcement of overbroad covenants
        - Standards for preliminary injunctions in restrictive-covenant disputes (irreparable harm presumption or not; delay as a defense)
        - Tortious interference with contract vs. prospective economic advantage — elements and distinctions
   4. Illinois Rules of Civil Procedure / local circuit court rules on venue, emergency motion practice, and TRO/preliminary injunction procedure (including any bond requirement)
   5. [AUTHORITY TO FIND] any recent amendments (post-2022) to the Illinois non-compete statute and their retroactivity/applicability to agreements signed before the amendment

Databases / resources to search:
   - Westlaw or Lexis (Illinois state case law and statutes, KeyCite/Shepard's to confirm currency and validity of any case located)
   - Illinois Compiled Statutes (official state legislative website) for current statutory text and legislative history
   - Illinois courts' official appellate/supreme court opinion archives
   - Casetext or Fastcase as a secondary check if available
   - Illinois CLE / ISBA (Illinois State Bar Association) practice materials and treatises on employment/restrictive covenants for background and element checklists (secondary source only — verify against primary law)
   - Bloomberg Law or Practical Law (if available) for a current practice note on Illinois non-compete law and trade secrets, as an orientation tool before drafting

Suggested search terms (to run across the above databases):
   - "Illinois" + "non-compete" + "reasonableness" + "legitimate business interest"
   - "Illinois" + "restrictive covenant" + "near-permanent customer relationship"
   - "Illinois" + "non-compete" + "adequate consideration" + "continued employment"
   - "Illinois" + "freedom to work" + "earnings threshold" + "non-compete" OR "non-solicitation"
   - "Illinois" + "non-compete" + "advise" + "consult an attorney" + "14 days" (or similar notice-period phrasing)
   - "Illinois" + "blue pencil" + "restrictive covenant" + "modify" OR "reform"
   - "Illinois" + "preliminary injunction" + "non-compete" + "irreparable harm"
   - "Illinois trade secrets act" + "customer list" + "misappropriation"
   - "Illinois" + "tortious interference" + "business relationship" + "customer solicitation"
   - "Illinois" + "choice of law" + "non-compete" + "void"

Deliverable from this stage: a short memo (after the above primary-source research is actually completed) confirming (i) whether the statutory earnings threshold excludes this employee from non-compete enforceability (but query whether a narrower non-solicitation covenant might survive even if the non-compete does not), (ii) whether consideration was adequate given the signing timeline, (iii) whether the client's facts support a legitimate business interest, and (iv) a realistic assessment of injunctive relief given the time already elapsed since resignation. All conclusions must be confirmed against current, Shepardized/KeyCited primary authority by a licensed Illinois attorney before being communicated to the client as legal advice.

