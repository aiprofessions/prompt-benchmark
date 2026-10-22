# Transcript — law-en-research-memo-01 — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:55:01+00:00
- duration_s: 51.0
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

PRELIMINARY ISSUE MEMO: Sample Bakery LLC v. R. Example (Illinois)

Every point below is a general starting framework, not legal advice. Each point, including thresholds, dates, elements, and remedies, must be verified in current primary sources by a licensed Illinois attorney before anyone relies on it.

BOTTOM LINE

The non-compete itself is likely unenforceable. Illinois's employee non-compete statute, as amended for agreements entered on or after January 1, 2022, generally voids non-competes for employees earning $75,000 or less per year [AUTHORITY TO FIND]. R. Example's $48,000 salary is well under that threshold.

The stronger path is probably a customer non-solicitation theory. The statute appears to set a lower earnings threshold for non-solicits, generally understood to be $45,000 [AUTHORITY TO FIND], and $48,000 may clear it. That path only works if the contract contains a non-solicit clause, or if the non-compete's language can be read or severed that way.

Other options are trade secret, duty of loyalty, and tortious interference claims.

Filing on the non-compete alone carries real risk. The statute is understood to award attorney's fees to an employee who prevails against enforcement [AUTHORITY TO FIND].

1. LEGAL ISSUES

  Q1. Is the non-compete void under Illinois's non-compete statute because of R. Example's earnings, and does the statute govern a 2022 agreement?

  Q2. Even if not barred by earnings, is the covenant reasonable and enforceable? That covers legitimate business interest, adequate consideration, and reasonable scope (2 years, 100 miles, "any baked-goods sales").

  Q3. Did the agreement meet the statute's procedural requirements: written advice to consult an attorney and at least 14 calendar days to review?

  Q4. Does the agreement contain a customer non-solicitation covenant, and is it enforceable at his earnings level and as applied to the café customers?

  Q5. If a covenant is overbroad, will an Illinois court reform or blue-pencil it, or strike it entirely?

  Q6. Are there non-contractual claims? Candidates are misappropriation of trade secrets (customer lists, pricing, order history), breach of the duty of loyalty for pre-resignation conduct, and tortious interference with customer relationships or prospective economic advantage.

  Q7. Can the client get a TRO or preliminary injunction, and what is its fee and damages exposure if it loses?

  Q8. Does the competing bakery face liability, for example tortious interference with contract or trade secret misappropriation?

2. ELEMENTS / FACTORS (as generally understood; verify each)

  Q1 – Statutory earnings bar
    - Date the agreement was entered (on or after Jan 1, 2022, triggers the amended statute) [AUTHORITY TO FIND]
    - Definition of "earnings": what compensation counts (base, commissions, bonuses) and over what period [AUTHORITY TO FIND]
    - His actual or expected annualized earnings compared to the threshold
    - Whether threshold step-ups scheduled for later years matter (generally no, since the governing date is when the agreement was entered) [AUTHORITY TO FIND]

  Q2 – Reasonableness (statutory codification of common law)
    - Covenant is no greater than required to protect a legitimate business interest
    - It does not impose undue hardship on the employee
    - It is not injurious to the public
    - Legitimate business interest is judged on the totality of circumstances, e.g. near-permanent customer relationships, confidential information, the employee's access to them [AUTHORITY TO FIND]
    - Adequate consideration: generally at least 2 years of continued employment after signing, or other professional or financial benefits [AUTHORITY TO FIND]. Employment ran 2022 to Aug 2026, so this is likely satisfied; confirm the exact dates.
    - Scope: whether the duration, the geography, and the activity restriction ("any baked-goods sales") are tailored to his actual territory and customers

  Q3 – Procedural requirements
    - Employer advised the employee in writing to consult an attorney before signing
    - Employee had at least 14 calendar days to review [AUTHORITY TO FIND]

  Q4 – Non-solicitation
    - A clause actually restricts soliciting customers or employees
    - He meets the earnings threshold for non-solicits
    - Same reasonableness and consideration analysis as Q2
    - Café customers were his accounts, or he had access to confidential information about them
    - Evidence of actual solicitation, as opposed to customers approaching him

  Q5 – Reformation
    - Court has discretion to reform or sever, weighing the extent of overbreadth and the employer's good faith in drafting [AUTHORITY TO FIND]
    - Any severability or reformation clause in the contract

  Q6 – Alternative claims
    - Trade secrets: information qualifies as a trade secret, meaning it is not generally known, derives value from secrecy, and is subject to reasonable secrecy measures; plus misappropriation and damages [AUTHORITY TO FIND]. Customer identities of cafés are often readily ascertainable, so focus on pricing, volumes, terms, and order histories.
    - Duty of loyalty: whether he solicited customers or diverted business while still employed [AUTHORITY TO FIND]
    - Tortious interference: a reasonable expectancy or contract, defendant's knowledge, intentional and unjustified interference, and damages [AUTHORITY TO FIND]

  Q7 – Preliminary injunction
    - A clearly ascertainable right in need of protection
    - Irreparable harm
    - No adequate remedy at law
    - Likelihood of success on the merits
    - Balance of hardships, and possibly the public interest [AUTHORITY TO FIND]
    - Bond requirement [AUTHORITY TO FIND]
    - Fee exposure: employee's recovery of fees if he prevails against enforcement, plus any contractual fee clause [AUTHORITY TO FIND]

3. FACTS NEEDED FROM CLIENT

  Agreement
    - Full signed agreement and any amendments; exact execution date
    - Whether it contains non-solicit, confidentiality, choice-of-law, venue, severability, tolling, or fee-shifting clauses
    - Whether he was advised in writing to consult counsel and how long he had to review
    - Whether he signed before or after starting work, and what consideration was given

  Compensation
    - Full compensation history 2022–2026: base, commissions, bonuses, W-2 totals
    - Any raises (relevant to the earnings threshold calculation)

  Employment
    - Exact start and resignation dates; circumstances of departure
    - His territory, accounts, and role
    - What confidential information he accessed: pricing, margins, customer order data, recipes
    - Confidentiality measures in place: NDAs, access controls, password protection, policies

  Conduct
    - Which café customers he contacted, when, how, and what he said
    - Any lost or reduced orders, with dollar amounts
    - Whether he took, emailed, or downloaded files before leaving (forensic review of devices and accounts)
    - Whether he solicited customers or coworkers before resigning
    - Whether he returned company property

  Competitor
    - Identity of the competing bakery and its knowledge of the agreement
    - Whether the client has sent a cease-and-desist letter yet

  Client goals
    - Injunction, damages, or a negotiated standstill
    - Budget, and tolerance for fee-shifting risk

4. RESEARCH PLAN

  Primary sources
    - Illinois non-compete statute as amended effective 2022: the full text, definitions of "earnings," thresholds, procedural requirements, reformation provisions, remedies and fees, and effective-date and applicability provisions [AUTHORITY TO FIND]
    - Illinois trade secrets statute [AUTHORITY TO FIND]
    - Illinois rules and code provisions on TROs, preliminary injunctions, and bonds [AUTHORITY TO FIND]
    - Illinois Supreme Court and Appellate Court decisions on legitimate business interest, consideration, reformation, and injunctions in restrictive-covenant cases [AUTHORITY TO FIND]
    - Federal developments: confirm the current status of any FTC non-compete rule or enforcement activity [AUTHORITY TO FIND]
    - Check for any Illinois legislative amendments enacted in 2025–2026

  Databases
    - Westlaw or Lexis: Illinois statutes (annotated), Illinois state cases, Seventh Circuit and N.D. Ill. cases applying Illinois law
    - Illinois General Assembly website for statute text and public act history
    - Bloomberg Law or Practical Law: Illinois non-compete practice notes and state survey charts
    - Secondary sources: IICLE practice handbooks, ISBA publications, law firm alerts on the 2022 amendments (use only to locate primary authority)
    - Check Illinois appellate courts' recent opinions and Rule 23 orders, noting their citation limits [AUTHORITY TO FIND]

  Suggested search terms
    - "covenant not to compete" /s earnings /s threshold & Illinois
    - "covenant not to solicit" /p "$45,000" OR earnings
    - "Freedom to Work" & (amend! /s 2022)
    - "legitimate business interest" /p "totality of the circumstances" & noncompet!
    - "adequate consideration" /p "two years" & restrictive covenant
    - noncompet! /p (reform! OR "blue pencil" OR modif!) /p overbroad!
    - "14 calendar days" /p "consult with an attorney"
    - noncompet! /p "attorney's fees" /p employee /p prevail!
    - "customer list" /p "trade secret" /p (readily ascertainable OR publicly available)
    - "duty of loyalty" /p solicit! /p before resign!
    - "preliminary injunction" /p "clearly ascertainable right" /p restrictive covenant
    - tortious interference /p former employee /p competitor /p customer
    - Key headnotes: Contracts – restraint of trade; Employment – covenants not to compete; Injunctions – preliminary

  Suggested sequence
    1. Read the statute and confirm whether the earnings bar applies (this may be dispositive on the non-compete).
    2. Review the actual agreement for a non-solicit clause and for procedural compliance.
    3. Research the alternative claims.
    4. Assess fee exposure before any filing or demand letter.

Reminder: no authority has been identified here. Every legal point, threshold, and element must be located and verified in primary sources by a licensed Illinois attorney.

