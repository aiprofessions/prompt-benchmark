# Transcript — law-en-research-memo-01 — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:40:24+00:00
- duration_s: 57.3
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

PRELIMINARY ISSUE MEMO: Sample Bakery LLC v. R. Example (non-compete, Illinois)

Every point below must be verified in primary sources by a licensed attorney. This outline reflects general understanding only, may be outdated or incomplete, and is not legal advice.

Bottom line for triage: Illinois restricts non-competes by statute for lower-earning employees. A $48,000 base salary may fall below the earnings threshold for non-competes. If so, the non-compete is likely unenforceable as written, and the client's realistic remedies are a non-solicitation theory (if the earnings threshold for those is met and such a clause exists), trade secret and confidentiality claims, and claims based on pre-resignation conduct. Confirm total earnings first. Commissions and bonuses may change the analysis.

1. LEGAL ISSUES

  Q1. Is the non-compete barred by Illinois statute because of R. Example's earnings, given that the agreement was signed in 2022?
  Q2. If not barred, is the non-compete enforceable under Illinois reasonableness standards (legitimate business interest, duration, geography, scope of activity) and supported by adequate consideration?
  Q3. Did the agreement satisfy the statute's procedural requirements (written advice to consult counsel, minimum review period)?
  Q4. Does the agreement contain a separate customer non-solicitation clause, and is it enforceable, including under its own earnings threshold?
  Q5. If any restriction is overbroad (e.g., "any baked-goods sales," 100 miles), will an Illinois court modify ("blue-pencil" or reform) it, or decline to enforce it entirely?
  Q6. Independent of the contract, does the client have claims for trade secret misappropriation, breach of a confidentiality covenant, breach of the duty of loyalty (pre-resignation conduct), or tortious interference with customer relationships, and could the new employer be liable?
  Q7. Can the client get a TRO or preliminary injunction, and on what showing?
  Q8. What is the client's exposure if it sues and loses? This includes a possible statutory fee-shifting provision favoring employees who successfully resist enforcement.
  Q9. Do any contractual terms (choice of law, forum, fee clause, tolling, assignment) or any federal developments affect the analysis?

2. ELEMENTS / FACTORS (as generally understood)

  Q1. Statutory earnings bar [AUTHORITY TO FIND]
    - Date of agreement. My understanding is that the statute applies to agreements entered into on or after January 1, 2022. Confirm the exact signing date.
    - Earnings threshold. My understanding is that non-competes are void for employees whose actual or expected annualized earnings are at or below about $75,000. Non-solicits are void at or below about $45,000. Both thresholds are scheduled to increase periodically. Verify the amounts, which threshold date applies, and how "earnings" is defined. The definition likely includes commissions and bonuses.
    - Other categorical exclusions, such as certain COVID-era or collective bargaining provisions. Likely irrelevant, but confirm.

  Q2. Common-law and statutory reasonableness [AUTHORITY TO FIND]
    - Legitimate business interest, judged on the totality of circumstances. Factors include near-permanent customer relationships, access to confidential information, and the nature of the business.
    - The restraint is no greater than necessary to protect that interest.
    - No undue hardship on the employee.
    - No injury to the public.
    - Reasonableness of duration (2 years), geography (100 miles, compared with where the client actually does business), and activity scope (all baked-goods sales, not limited to the client's customers or product lines).
    - Adequate consideration. My understanding is that this requires at least about two years of continued employment after signing, or other professional or financial benefits. Employment from 2022 to August 2026 likely satisfies this, but verify the rule and confirm the exact dates.

  Q3. Procedural prerequisites [AUTHORITY TO FIND]
    - The employee was advised in writing to consult an attorney before signing.
    - The employee was given a minimum review period (my understanding: 14 calendar days).
    - The consequence of noncompliance (likely unenforceability).

  Q4. Non-solicitation
    - A clause exists and covers customers the employee dealt with or learned about.
    - The earnings threshold for non-solicits is met.
    - The same reasonableness and consideration analysis as Q2 applies.
    - Whether café customers are "customers of the employer" within the clause.

  Q5. Modification / reformation [AUTHORITY TO FIND]
    - Court discretion. Factors may include the extent of the overbreadth, whether the drafter acted in good faith, and whether the agreement has a reformation or severability clause.
    - Illinois courts have sometimes refused to rewrite grossly overbroad covenants. The statute may address this.

  Q6. Non-contract claims
    - Trade secret misappropriation [AUTHORITY TO FIND]: (a) information qualifies as a trade secret (customer lists, pricing, order histories, margins); (b) reasonable secrecy measures; (c) acquisition, use, or disclosure by improper means or in breach of a duty. Consider whether "inevitable disclosure" is recognized in Illinois.
    - Breach of confidentiality covenant: valid clause, confidential information, breach, damages.
    - Breach of fiduciary duty / duty of loyalty: limited to conduct while still employed, such as soliciting customers or taking documents before resignation.
    - Tortious interference with prospective economic advantage: (a) reasonable expectancy of a continued business relationship; (b) defendant's knowledge; (c) intentional, unjustified interference; (d) damages. Competition privilege issues apply.
    - New employer liability: tortious interference with contract, or aiding and abetting.

  Q7. Preliminary injunction [AUTHORITY TO FIND]
    - Clearly ascertainable right in need of protection.
    - Irreparable harm (loss of customer goodwill is often argued).
    - No adequate remedy at law.
    - Likelihood of success on the merits.
    - Balance of hardships and the public interest.
    - Bond requirement.

  Q8. Fee-shifting exposure [AUTHORITY TO FIND]
    - My understanding is that the statute lets a prevailing employee recover attorney's fees when an employer sues to enforce a covenant. Verify the scope and whether any contractual fee clause interacts with it.
    - Possible Attorney General enforcement for a pattern of unlawful covenants. This matters if the client uses the same form for other low-wage staff.

  Q9. Other
    - Choice of law and forum clauses.
    - Tolling clause (extending the 2 years during a breach).
    - Status of any federal non-compete rule or FTC enforcement position as of October 2026 [AUTHORITY TO FIND].

3. FACTS NEEDED FROM CLIENT

  Agreement and formation
    - The full signed agreement and any amendments. Exact signing date versus start date.
    - Whether the agreement was signed before or after the first day of work, and what consideration was given.
    - Any written advice to consult counsel, and how long he had to review it (emails, offer letter).
    - Whether there are separate non-solicit, confidentiality, non-disparagement, choice-of-law, forum, fee, tolling, or reformation clauses.
    - Whether the same form is used for other employees.

  Compensation
    - Total actual earnings each year, 2022 to 2026, including commissions, bonuses, and overtime (W-2s).
    - Expected earnings at hiring.
    - Raises.

  Employment and departure
    - His role, territory, and the customers he personally handled.
    - What confidential information he accessed (pricing, cost data, order volumes, recipes, CRM).
    - Exact resignation date.
    - Exit interview and any acknowledgment of obligations.
    - Return of devices and documents. Any downloads, forwarding to personal email, or CRM exports before he left (forensic review).
    - Any solicitation or competitor contact before resignation.

  Post-departure conduct and harm
    - The competitor's identity and location, and whether it knew of the covenant.
    - Which customers he has contacted, how the client learned of it, and the evidence (emails, texts, customer statements).
    - Customers lost or reduced, revenue impact, and timing.
    - Whether he is using client pricing or other information.

  Business interest
    - The client's actual service area and customer locations relative to the 100-mile radius.
    - Customer relationship length and stability.
    - Secrecy measures (passwords, NDAs, access limits).
    - Whether any cease-and-desist letter has been sent, and any response.
    - Any delay in acting. Delay can undercut irreparable harm.

4. RESEARCH PLAN

  Primary sources
    - Illinois Compiled Statutes: the restrictive-covenant-in-employment statute (as amended effective 2022), including the definitions, earnings thresholds and adjustment schedule, the consideration, notice and review-period provisions, the reformation and fee-shifting provisions, and Attorney General enforcement. Also the Illinois trade secrets statute. [AUTHORITY TO FIND]
    - Legislative history of the 2021 amendments (Illinois General Assembly website: bill text, debate transcripts).
    - Illinois Supreme Court and Appellate Court decisions on: legitimate business interest, consideration adequacy, judicial reformation, preliminary injunctions in covenant cases, and any post-2022 decisions applying the earnings thresholds. Note appellate district splits. [AUTHORITY TO FIND]
    - Federal district court decisions applying Illinois law (N.D. Ill. especially). These are persuasive only.
    - Illinois Supreme Court Rules and the Code of Civil Procedure on TROs, preliminary injunctions, and bonds. [AUTHORITY TO FIND]
    - Current federal developments: FTC non-compete rule litigation status and any federal legislation.

  Databases
    - Westlaw / Lexis / Bloomberg Law: case law, KeyCite/Shepard's for every authority, statute annotations.
    - Fastcase/vLex (via ISBA membership), Illinois Courts website for recent appellate opinions, including Rule 23 orders. Verify the citability rules for those orders.
    - Secondary: IICLE practice handbooks on employment law and restrictive covenants, the Illinois Bar Journal, Practical Law / Lexis Practice Advisor state Q&A on Illinois non-competes, and law firm client alerts (as leads only, then verify).

  Suggested search terms
    - "covenant not to compete" AND Illinois AND (earnings OR "$75,000" OR threshold)
    - "covenant not to solicit" AND Illinois AND "$45,000"
    - "adequate consideration" AND "two years" AND "continued employment" AND Illinois
    - "legitimate business interest" AND "totality of the circumstances" AND restrictive covenant
    - "near-permanent" AND customer AND Illinois AND covenant
    - (reform OR modify OR "blue pencil") AND overbroad AND covenant AND Illinois
    - "14 calendar days" OR "consult with an attorney" AND covenant AND Illinois
    - "attorney's fees" AND prevail AND employee AND covenant AND Illinois
    - "preliminary injunction" AND "clearly ascertainable right" AND covenant
    - "trade secret" AND "customer list" AND Illinois AND (bakery OR distributor OR route sales)
    - "inevitable disclosure" AND Illinois
    - "tortious interference" AND "prospective economic advantage" AND former employee AND Illinois
    - "duty of loyalty" AND resign AND solicit AND Illinois

  Suggested sequence
    1. Get the agreement and W-2s. Determine whether the earnings bar is dispositive.
    2. If the non-compete is likely void, pivot to the non-solicit, confidentiality, and trade secret theories, and assess fee-shifting risk before filing.
    3. Evaluate the evidence for pre-resignation misconduct and a forensic device review.
    4. Assess injunction timing. Delay weakens irreparable harm.
    5. Consider a cease-and-desist letter to the employee and the new employer as an early, lower-risk step.

Reminder: all of the above, including the stated thresholds, dates, review period, and elements, is based on general understanding and must be verified in current primary sources by a licensed Illinois attorney before any reliance or advice to the client.

