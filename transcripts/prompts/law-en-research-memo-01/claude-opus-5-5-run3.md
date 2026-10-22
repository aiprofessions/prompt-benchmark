# Transcript — law-en-research-memo-01 — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:10:30+00:00
- duration_s: 46.3
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

Every point below is preliminary and must be verified in primary sources by a licensed Illinois attorney before anyone relies on it. No authority is cited; [AUTHORITY TO FIND] marks where support is needed.

1. LEGAL ISSUES

  I-1  Does the Illinois statute restricting employee non-competes apply to this agreement, and does it bar enforcement because of R. Example's earnings level? [AUTHORITY TO FIND]

  I-2  If the statute does not bar it, is the covenant enforceable under Illinois law: legitimate business interest, adequate consideration, and reasonable scope (2 years, 100 miles, all baked-goods sales)? [AUTHORITY TO FIND]

  I-3  Does the agreement contain a separate customer non-solicitation clause, and is it enforceable even if the non-compete is not? The statute appears to set a lower earnings threshold for non-solicits than for non-competes. [AUTHORITY TO FIND]

  I-4  If any clause is overbroad, will an Illinois court modify ("blue-pencil" or reform) it, or refuse to enforce it entirely? [AUTHORITY TO FIND]

  I-5  Independent of the contract, is there a trade secret misappropriation claim under Illinois and/or federal trade secret law (customer lists, pricing, order histories)? [AUTHORITY TO FIND]

  I-6  Are there other claims, such as breach of the duty of loyalty for pre-resignation conduct, tortious interference with customer relationships, or claims against the competing bakery? [AUTHORITY TO FIND]

  I-7  Can the client get a TRO or preliminary injunction, and what is the fee and cost exposure if it loses? The statute appears to let a prevailing employee recover attorney's fees. [AUTHORITY TO FIND]

2. ELEMENTS / FACTORS (as generally understood)

  I-1  Statutory applicability
    - Agreement date relative to the statute's effective date (amendments effective around January 1, 2022). Verify whether pre-effective-date agreements are governed by prior common law.
    - The employee's "earnings" against the statutory thresholds. My recollection: non-competes are void for employees earning $75,000/yr or less, and non-solicits for $45,000/yr or less, with scheduled increases (including in 2027). Verify the figures, the measuring date, and whether commissions and bonuses count.
    - Procedural requirements. These may include advising the employee in writing to consult counsel and giving at least 14 days to review.
    - Whether the employee was laid off or furloughed for COVID-type reasons. This likely does not apply because he resigned.
    - If the reported $48,000 base is his total earnings, the non-compete looks likely void under the statute. A non-solicit may survive because he exceeds the lower threshold. This is the central question to confirm first.

  I-2  Common-law enforceability
    - Legitimate business interest. Courts weigh the totality of circumstances, such as near-permanent customer relationships, confidential information, and the employee's access to customers. [AUTHORITY TO FIND]
    - Adequate consideration. This is roughly two years of continued employment or other professional or financial benefits. He worked about 4 years, if hired in 2022 and resigned in 2026. [AUTHORITY TO FIND]
    - Reasonableness. The restriction must be no greater than needed, must not unduly burden the employee, and must not harm the public. Weak points here are the 100-mile radius and the "any baked-goods sales" scope.

  I-3  Non-solicitation
    - Whether a clause exists, the earnings threshold, and reasonable scope. Scope typically covers customers he actually dealt with or learned about, over a reasonable time period.

  I-4  Reformation
    - Courts have discretion. Factors include the extent of overbreadth, the fairness of the drafting, and any reformation clause in the contract. [AUTHORITY TO FIND]

  I-5  Trade secrets
    - Information is secret, derives value from secrecy, and is subject to reasonable secrecy measures.
    - Misappropriation (acquisition, use, or disclosure by improper means or breach of duty).
    - Customer identities that are publicly ascertainable (e.g., cafés) may not qualify. Compiled data like pricing, volumes, and contacts may qualify. [AUTHORITY TO FIND]

  I-6  Other claims
    - Duty of loyalty: solicitation or diversion while still employed.
    - Tortious interference: a reasonable expectancy, the defendant's knowledge, purposeful interference, and damages.

  I-7  Preliminary injunction
    - A clearly ascertained right, irreparable harm, no adequate remedy at law, and likelihood of success on the merits.
    - Courts also balance hardships. [AUTHORITY TO FIND]

3. FACTS NEEDED FROM THE CLIENT

  - Exact signing date, and whether he signed at hire or later.
  - Full copy of the agreement: non-solicit, confidentiality, choice-of-law, forum, fee-shifting, reformation and tolling clauses.
  - Was he advised in writing to consult an attorney? How long did he have to review it?
  - Total annual earnings each year, including commissions, bonuses and other compensation (W-2s). Earnings in the year before termination are especially important.
  - Consideration given at signing, and anything given later.
  - His role: which customers he handled, how the relationships were built, and how long the client has served them.
  - What confidential information he accessed: pricing, margins, customer lists, CRM access. What secrecy measures were in place (NDAs, password controls, need-to-know)?
  - Whether he took, downloaded or emailed any files before leaving. Was his device or email reviewed (forensics)?
  - Any solicitation before his resignation.
  - Evidence of current solicitation: which customers, when, and what was said. Have any customers moved or reduced orders, and by how much in lost revenue?
  - Identity of the competing bakery, whether it knew of the agreement, and whether a cease-and-desist was sent.
  - Exit interview and return-of-property acknowledgment.
  - The client's geographic market, to test whether 100 miles matches the actual customer footprint.
  - Who drafted the agreement, and whether other employees signed the same form. This bears on consistency and reformation.
  - Litigation goals, budget, and tolerance for the risk of paying his attorney's fees if the client loses.

4. RESEARCH PLAN

  Primary sources
  - Illinois statutes: the employee non-compete statute, including its 2022 amendments, definitions of "earnings," thresholds, notice requirements, attorney's fee provision and effective date. Also the Illinois trade secrets act. [AUTHORITY TO FIND]
  - Federal trade secret statute, if federal court is considered. [AUTHORITY TO FIND]
  - Illinois Supreme Court and Appellate Court decisions on:
      - legitimate business interest (totality test)
      - adequacy of consideration
      - judicial reformation
      - preliminary injunctions in restrictive covenant cases
      - how the post-2022 statute has been applied
  - Federal district court decisions applying Illinois law. These are persuasive only.
  - Current status of any federal non-compete regulation. A prior FTC rule was set aside; confirm there is no current federal rule. [AUTHORITY TO FIND]
  - Legislative history of the 2022 amendments.
  - Illinois Supreme Court Rules and the Code of Civil Procedure on TROs and preliminary injunctions.

  Databases
  - Westlaw or Lexis: Illinois statutes annotated, Illinois cases, KeyCite or Shepard's for every authority.
  - Illinois General Assembly website for current statutory text and amendment history.
  - Illinois Courts website for recent appellate opinions, including Rule 23 orders. Check their citability.
  - Secondary sources: Illinois practice treatises on restrictive covenants, IICLE materials, the Illinois State Bar Association, and 50-state non-compete surveys. Use these only to locate primary authority.
  - Bloomberg Law or Lexis practical guidance for current threshold amounts.

  Suggested search terms
  - Illinois "Freedom to Work" non-compete earnings threshold
  - "covenant not to compete" void "earnings" Illinois 2022 amendment
  - Illinois "covenant not to solicit" earnings threshold
  - Illinois non-compete "adequate consideration" "two years" continued employment
  - Illinois "legitimate business interest" "totality of the circumstances" non-compete
  - Illinois non-compete "reformation" OR "blue pencil" overbroad
  - Illinois non-compete "attorney's fees" prevailing employee
  - Illinois "activity restraint" "any" industry overbroad sales employee
  - Illinois "customer list" trade secret "reasonable efforts" secrecy
  - Illinois "duty of loyalty" employee solicitation before resignation
  - Illinois "preliminary injunction" restrictive covenant "irreparable harm" customers
  - Illinois "tortious interference" competitor hiring employee non-compete

Bottom line for intake: the threshold question is whether his total earnings fell below the statutory non-compete threshold. If so, the non-compete is likely unenforceable as written. The realistic paths are then a non-solicit clause, if one exists and he exceeds its lower threshold, plus trade secret or loyalty claims. Confirm all of this in primary sources, with a licensed attorney's review.

