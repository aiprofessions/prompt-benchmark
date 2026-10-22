# Transcript — law-en-research-memo-01 — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:10:41+00:00
- duration_s: 99.2
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

NON-COMPETE ENFORCEMENT – PRELIMINARY RESEARCH FRAMEWORK
Sample Bakery LLC v. R. Example (fictional) — Illinois state court
PRIVILEGED / WORK PRODUCT – DRAFT FOR ATTORNEY REVIEW ONLY

Every substantive point below is a general framework only. No conclusion here should be relied on, cited, or communicated to the client as settled law. A licensed Illinois attorney must independently verify every proposition in primary sources (current statute text, effective-date provisions, and binding case law) before any advice is given or any pleading is filed. Placeholders [AUTHORITY TO FIND] mark every point requiring sourcing.

1. LEGAL ISSUES (as questions)

1. Is the 2022 covenant governed by Illinois's current restrictive-covenant statute, or by pre-statute common law, depending on the exact signing date and the statute's effective-date/grandfathering provisions? [AUTHORITY TO FIND]

2. Did the employee receive "adequate consideration" for the covenant under Illinois law, given that it was signed at hiring (as opposed to mid-employment), and does the compensation level satisfy any statutory earnings threshold for non-competes versus non-solicits? [AUTHORITY TO FIND]

3. Did the employer satisfy any statutory procedural prerequisites (e.g., advance notice before signing, written advisement of the right to consult counsel) that may be required for enforceability? [AUTHORITY TO FIND]

4. Does the covenant protect a "legitimate business interest" of the employer (e.g., near-permanent customer relationships, confidential pricing/customer data), as opposed to merely restraining ordinary competition? [AUTHORITY TO FIND]

5. Are the covenant's restrictions — 2-year duration, 100-mile radius, "any baked-goods sales" activity scope — reasonable in time, geography, and scope of restrained activity, or is the covenant overbroad? [AUTHORITY TO FIND]

6. What is the correct interpretation of the "2 years" term — does it run from the 2022 signing date or from the 2026 termination date? If it runs from signing, has the restricted period already expired, mooting enforcement? (This is a contract-interpretation question, not purely a research question, but it gates everything else.)

7. If the covenant is unenforceable or expired, does the employer have independent claims — trade secret/confidential information misappropriation, breach of duty of loyalty/fiduciary duty (if solicitation began pre-resignation), or tortious interference with business relationships against the employee or the new employer? [AUTHORITY TO FIND]

8. If some version of the covenant is valid but overbroad, will an Illinois court "blue-pencil" (judicially narrow) the covenant rather than void it entirely? [AUTHORITY TO FIND]

9. What remedy is available and on what standard — preliminary injunction/TRO (and its elements), damages, liquidated damages or fee-shifting if the contract contains such clauses? [AUTHORITY TO FIND]

10. Are there venue, choice-of-law, or choice-of-forum clauses in the agreement that affect where and how suit must be brought? [AUTHORITY TO FIND]

2. ELEMENTS / FACTORS GENERALLY UNDERSTOOD FOR EACH ISSUE

A. Enforceability of a restrictive covenant (general Illinois framework)
 - Valid underlying contract with adequate consideration
 - Covenant ancillary to a valid employment relationship
 - Covenant protects a legitimate business interest of the employer
 - Covenant is reasonable in: (i) duration, (ii) geographic scope, (iii) scope of activity restrained
 - Covenant is not injurious to the public
 - Covenant is not greater than required to protect the employer's interest, and not oppressive to the employee
 - Compliance with any statutory thresholds/procedures (earnings minimum, notice period, right-to-counsel advisement), if applicable to agreements of this vintage
 [AUTHORITY TO FIND for current statutory text, effective date, and the operative common-law multi-factor test]

B. "Legitimate business interest" — typical factors (totality-of-circumstances approach)
 - Near-permanent nature of customer relationships (duration, exclusivity, difficulty of developing replacements)
 - Employee's acquisition of confidential information or trade secrets through the employment
 - Restricted geographic area relative to employer's actual area of business
 - Time restriction relative to how long it would take a competitor to neutralize the advantage
 - Whether the restriction is tied to the employee's actual role or overreaches into unrelated business lines
 [AUTHORITY TO FIND]

C. Adequate consideration
 - Whether signing was a condition of the job offer itself (at-hire) versus imposed mid-employment
 - If continued employment is the sole consideration, whether a minimum period of continued at-will employment is required, and what that period is under current Illinois authority
 - Any additional consideration (bonus, raise, stock, training) exchanged for the covenant
 [AUTHORITY TO FIND]

D. Statutory thresholds/procedures (if the current statute applies to this agreement)
 - Minimum annualized earnings threshold for non-compete enforceability (and a separate, generally lower, threshold for customer non-solicitation covenants)
 - Required advance notice period before signing / opportunity to review
 - Required written advisement of right to consult an attorney
 - Consequences of non-compliance (unenforceability, fee-shifting exposure)
 [AUTHORITY TO FIND — exact dollar thresholds, notice period length, and effective date of statute relative to 2022 signing]

E. Reasonableness of time/geography/scope
 - Hardship to the employee
 - Effect on the public/consumers
 - Employer's actual trade territory versus the stated radius
 - Whether "any baked-goods sales" restraint matches the employee's actual sales role or improperly restrains unrelated activity
 [AUTHORITY TO FIND]

F. Blue-penciling / reformation
 - Whether Illinois courts will modify an overbroad covenant to a reasonable scope rather than void it outright, and under what circumstances
 [AUTHORITY TO FIND]

G. Trade secret / confidential information misappropriation (alternative/additional claim)
 - Existence of information qualifying as a trade secret (not generally known, independent economic value, reasonable protective measures taken)
 - Misappropriation (improper acquisition, use, or disclosure)
 - Resulting damages or unjust enrichment
 [AUTHORITY TO FIND — Illinois trade secrets statute and case law]

H. Breach of fiduciary duty / duty of loyalty (if applicable)
 - Existence of a duty owed while still an employee
 - Breach (e.g., soliciting customers or diverting business before resignation)
 - Causation and damages
 [AUTHORITY TO FIND]

I. Tortious interference with business relationship/expectancy (against employee or competitor)
 - Reasonable expectation of continued business relationship with specific customers
 - Interferer's knowledge of that relationship
 - Intentional and unjustified interference
 - Resulting damages
 [AUTHORITY TO FIND]

J. Preliminary injunction / TRO standard
 - Likelihood of success on the merits
 - Irreparable harm without an adequate remedy at law (and whether Illinois law presumes irreparable harm in covenant cases or requires proof)
 - Balance of hardships
 - Public interest
 [AUTHORITY TO FIND]

3. FACTS STILL NEEDED FROM THE CLIENT

Contract-specific
 - Exact date the agreement was signed in 2022 (day/month), and whether signing occurred before, at, or after the employee's actual start date
 - Exact contract language defining the "2-year" period — does it run from signing or from separation/termination? Any tolling provision?
 - Exact language defining the 100-mile radius — measured from what point (headquarters, warehouse, each customer's location)?
 - Whether the agreement contains a separate confidentiality clause and/or a separate non-solicitation-of-customers or non-solicitation-of-employees clause (distinct from the broader non-compete)
 - Whether the agreement contains a liquidated damages clause, attorney-fee-shifting clause, choice-of-law clause, or forum-selection clause
 - Whether the employer gave the employee advance notice before signing and/or a written advisement of the right to consult counsel

Compensation
 - Total annualized compensation at hiring and at separation (base + commission + bonus), not just the $48,000 base, since sales roles often include variable pay relevant to any statutory earnings threshold

Employment/role facts
 - Employee's actual job title and duties (was he solely a wholesale sales rep to cafés, or broader?)
 - Whether he had access to confidential customer lists, pricing, margins, or supplier information, and what safeguards (NDAs, access controls, marked-confidential documents) protected that information
 - Whether he returned company property (laptop, phone, documents, customer lists) on departure, and whether any forensic review has been done

Conduct at issue
 - Specific café customers he has contacted since joining the competitor, and how he obtained their contact information (public knowledge vs. taken from client's systems)
 - Whether solicitation began before his August 2026 resignation (while still employed) or only afterward
 - Dollar value/significance of the customers/revenue at risk
 - Exact location of the new employer's business and of the solicited customers relative to the 100-mile radius and the "measured from" point in the contract

Practice/history
 - Whether the client has enforced similar covenants against other former employees before, or has a pattern of non-enforcement (potential waiver/estoppel argument by the defense)
 - Whether client has already sent a cease-and-desist or demand letter, and if so, employee's/competitor's response
 - Date client first learned of the competing employment and the solicitation (relevant to laches/delay in seeking injunctive relief)

Entity/jurisdictional
 - Confirmation that Illinois law governs (no conflicting choice-of-law clause) and the county where the client, employee, and relevant conduct are located (for venue)
 - Employer's size/structure, in case any statutory exemption for small employers or specific industries applies

4. RESEARCH PLAN

Primary sources to check
 - Illinois Compiled Statutes (current text) via the Illinois General Assembly's official site and Westlaw/Lexis annotated versions — for the restrictive-covenant statute's earnings thresholds, effective date/grandfather clause, and any notice/advisement requirements
 - Illinois Supreme Court and Appellate Court opinions (via Westlaw, Lexis, or the Illinois Courts website) on: the "legitimate business interest" test, adequate consideration for covenants signed at hiring vs. mid-employment, reasonableness of time/geography/scope, and blue-penciling/reformation practice
 - Illinois trade secrets statute and case law (Westlaw/Lexis) for any misappropriation claim
 - Illinois case law on tortious interference with business expectancy and breach of fiduciary duty/duty of loyalty by employees
 - Illinois case law and local circuit court rules on preliminary injunction/TRO standards in employment-covenant disputes, including the applicable circuit's specific procedures for emergency injunctive relief
 - Secondary sources (non-citable, for orientation only): Illinois CLE practice guides and employment-law treatises summarizing the 2022 statutory amendments, used only to identify primary authority to then verify directly

Databases
 - Westlaw (Illinois state case law, statutes annotated, secondary sources, KeyCite for currency)
 - Lexis+ (Illinois case law, Shepard's for currency)
 - Illinois General Assembly website (official current statutory text)
 - Illinois Courts website (published opinions)
 - County circuit court e-filing/docket system (for local rules on emergency motions, if litigation is contemplated)

Suggested search terms
 - "restrictive covenant" Illinois statute earnings threshold effective date
 - Illinois non-compete "legitimate business interest" totality of circumstances
 - Illinois "adequate consideration" non-compete continued employment length
 - Illinois non-solicitation customer covenant earnings threshold
 - Illinois "blue pencil" OR "reformation" restrictive covenant
 - Illinois preliminary injunction non-compete "irreparable harm"
 - Illinois trade secret misappropriation customer list sales employee
 - Illinois tortious interference business expectancy former employee
 - Illinois duty of loyalty employee solicitation before resignation
 - Illinois non-compete statute "notice period" "right to consult an attorney"
 - Illinois non-compete geographic radius reasonableness wholesale sales

Next step for the assigned attorney: pull the current statutory text and confirm its effective date and threshold figures first, since the answer to issue 1 (which legal regime applies) and issue 6 (whether the 2-year term has already run) will determine how much of the remaining research is even necessary.

