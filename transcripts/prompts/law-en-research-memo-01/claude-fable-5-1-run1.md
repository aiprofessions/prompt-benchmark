# Transcript — law-en-research-memo-01 — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:10:12+00:00
- duration_s: 86.3
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

Preliminary research framing — Sample Bakery LLC v. R. Example (Illinois state court)

Every point below is a general statement of how these issues are commonly analyzed. Nothing here is verified authority. Each element, threshold, and procedural requirement must be confirmed in primary sources by a licensed Illinois attorney before being relied on or communicated to the client.


1. LEGAL ISSUES (framed as questions)

  Issue A. Is the 2022 non-compete enforceable at all under Illinois's restrictive-covenant statute, given the employee's $48,000 base salary?

  Issue B. If the statutory threshold is met (or the agreement is construed as something other than a non-compete), was the agreement validly formed: adequate consideration, required notice/review period, and advice to consult counsel?

  Issue C. Does the covenant protect a legitimate business interest of the bakery, and are its terms (2 years, 100 miles, all baked-goods sales) reasonable in scope, or overbroad?

  Issue D. If overbroad, will an Illinois court modify ("blue-pencil"/reform) the covenant rather than strike it entirely, and does the agreement authorize that?

  Issue E. Independent of the covenant, does the employee's contact with café customers give rise to a claim for trade-secret misappropriation (customer list, pricing, volumes) under Illinois trade-secret law?

  Issue F. Does the bakery have a tortious-interference claim (with existing customer contracts or with prospective business relationships) against the employee and/or the competing bakery?

  Issue G. Did the employee breach any duty of loyalty or confidentiality obligation while still employed (e.g., soliciting customers or copying data before resigning in August 2026)?

  Issue H. Can the bakery obtain a temporary restraining order or preliminary injunction, and what showing is required?

  Issue I. What is the bakery's exposure if it sues and loses — specifically, statutory attorney-fee shifting to a prevailing employee and any state enforcement risk?


2. ELEMENTS / FACTORS FOR EACH ISSUE (as generally understood)

  Issue A — Statutory earnings threshold
    Illinois's restrictive-covenant statute, for agreements entered on or after its 2022 effective date, is generally understood to:
      - Void a non-compete for employees whose actual or expected annualized earnings fall below a statutory dollar threshold (commonly reported as well above $48,000 for non-competes). [AUTHORITY TO FIND]
      - Set a separate, lower threshold for customer/employee non-solicitation covenants. [AUTHORITY TO FIND]
      - Define "earnings" to include more than base salary (commissions, bonuses, etc. may count). [AUTHORITY TO FIND]
    Elements to establish: (i) agreement date relative to statutory effective date; (ii) employee's total annualized earnings at signing and at separation; (iii) whether the covenant is a "non-compete" or a "non-solicit" as the statute defines those terms.
    Practical note: on these facts the non-compete clause is at serious risk of being void by statute. Analysis may shift to whether any non-solicit or confidentiality language survives.

  Issue B — Valid formation
    Generally understood requirements under the current statute and Illinois common law:
      - Adequate consideration: either a minimum period of continued employment after signing (commonly described as two years) or other independent consideration (signing bonus, raise, etc.). [AUTHORITY TO FIND] Employee worked roughly four years post-signing, which likely helps.
      - Employer advised employee in writing to consult an attorney before signing. [AUTHORITY TO FIND]
      - Employee received the agreement a minimum number of days (commonly described as 14) before start date or signing. [AUTHORITY TO FIND]
      - Covenant is ancillary to a valid employment relationship.

  Issue C — Legitimate business interest and reasonableness
    Illinois courts are generally understood to apply a totality-of-circumstances test, considering:
      - Near-permanence of customer relationships (wholesale/café accounts may or may not qualify). [AUTHORITY TO FIND]
      - Employee's acquisition of confidential information through employment.
      - Time and territorial restrictions relative to the employer's actual trade area.
      - Whether the restriction is no greater than needed; not oppressive to the employee; not injurious to the public.
    Facts cutting against the client: 100-mile radius for a small wholesale bakery; "any baked-goods sales" without limit to the client's product lines or customers; two-year duration for a sales role.

  Issue D — Judicial modification
    Generally understood: Illinois courts have discretion to reform overbroad covenants but may refuse where the drafting is so broad it suggests bad faith; the statute is understood to list factors for when reformation is appropriate. [AUTHORITY TO FIND] Presence of a severability/modification clause is relevant but not controlling.

  Issue E — Trade-secret misappropriation
    Generally understood elements under the Illinois trade-secret statute: [AUTHORITY TO FIND]
      - Information qualifies as a trade secret: derives economic value from not being generally known; subject to reasonable secrecy measures.
      - Misappropriation: acquisition by improper means, or use/disclosure without consent by someone who knew or should have known the information was obtained improperly or under a duty of confidence.
      - Customer identity alone is often weak if cafés are discoverable from public sources; pricing, margins, order volumes, and renewal dates are stronger.
    Remedies commonly include injunction, damages, and in willful cases exemplary damages and fees.

  Issue F — Tortious interference
    With existing contract (generally understood): valid contract; defendant's knowledge; intentional and unjustified inducement of breach; actual breach; damages. [AUTHORITY TO FIND]
    With prospective economic advantage (generally understood): reasonable expectancy of a business relationship; defendant's knowledge; intentional and unjustified interference preventing the expectancy from ripening; damages. [AUTHORITY TO FIND]
    Competitor's privilege is a common defense where no wrongful means (misappropriation, fraud) are used.

  Issue G — Pre-departure breach of loyalty
    Generally understood: an employee may plan to compete but may not, while still employed, solicit the employer's customers for a competitor, divert business, or take confidential materials. [AUTHORITY TO FIND] Post-resignation conduct alone does not support this claim absent a surviving covenant.

  Issue H — TRO / preliminary injunction
    Generally understood Illinois factors: clearly ascertainable right needing protection; irreparable harm; no adequate remedy at law; likelihood of success on the merits; balance of hardships. [AUTHORITY TO FIND] Procedural rules on notice, bond, and verified pleading apply.

  Issue I — Downside exposure
    Generally understood: the restrictive-covenant statute provides for the employee to recover attorney fees and costs if the employee prevails in a suit to enforce a covenant. [AUTHORITY TO FIND] The state attorney general is understood to have enforcement authority over patterns of unlawful covenants. [AUTHORITY TO FIND]


3. FACTS STILL NEEDED FROM THE CLIENT

  The agreement
    - Full signed copy, exact date signed, and exact date employment began.
    - Was the agreement delivered to him at least 14 days before signing/start? Any proof (email, offer letter date)?
    - Does the document (or offer letter) advise him in writing to consult an attorney?
    - Does it contain, in addition to the non-compete: a customer non-solicitation clause, an employee non-solicitation clause, a confidentiality clause, a choice-of-law/venue clause, a severability or judicial-modification clause, a fee-shifting clause, a tolling clause?
    - Any later amendments, re-signings, or acknowledgments (e.g., at a raise or promotion)?

  Compensation
    - Total annualized earnings at signing and in the final 12 months: base, commissions, bonuses, car allowance, any other W-2 compensation. This is likely dispositive on Issue A.
    - Any signing bonus or other consideration tied specifically to the covenant.

  The employee's role
    - Job title, territory, which customers he handled, whether he had access to pricing, cost, margin, volume, and contract-renewal data.
    - Whether he was the sole point of contact for the café accounts.

  Confidential information
    - What customer/pricing information exists, where it is stored, and what access controls, confidentiality policies, and acknowledgments exist.
    - Any evidence he downloaded, emailed, or copied files before leaving (IT logs, device returns).
    - Whether the café customer list could be reconstructed from public sources (Google Maps, delivery routes, social media).

  Departure and post-departure conduct
    - Resignation letter and any exit interview notes; what he said he would do next.
    - Did he sign an exit acknowledgment of continuing obligations?
    - Evidence of pre-resignation solicitation (customer reports, calendar entries).
    - Specifically which customers he has contacted, when, what was said, and whether any have moved or reduced orders. Names of witnesses.
    - Whether he is using the same pricing or undercutting by a specific margin that suggests knowledge of client's pricing.

  The competitor
    - Name, location (confirm the 30 miles), whether it had notice of the covenant, and whether anyone at the client has already contacted it.

  The business
    - Client's actual sales radius and customer geography (to test the 100-mile term).
    - Nature of café relationships: written supply contracts or at-will purchase orders? Average tenure? Exclusivity?
    - Revenue at risk and ability to quantify loss.
    - Whether the client has sent any cease-and-desist letter yet.
    - Client's risk tolerance regarding fee exposure if the covenant is found void.


4. RESEARCH PLAN

  Databases
    - Westlaw and/or Lexis: Illinois Compiled Statutes (annotated), Illinois Supreme Court and Appellate Court decisions, and Northern/Central/Southern District of Illinois and Seventh Circuit decisions applying Illinois law.
    - Illinois General Assembly website (ilga.gov) for current statutory text and any amendments after 2022.
    - Illinois Attorney General website for any guidance or enforcement actions on restrictive covenants.
    - Illinois Supreme Court Rules and Code of Civil Procedure provisions on TROs, preliminary injunctions, and verified pleadings.
    - Secondary sources to orient only (never cited as authority): Illinois Institute for Continuing Legal Education (IICLE) treatises on employment and business litigation; Illinois Practice series; ABA/state bar practice notes; Westlaw Practical Law — Illinois non-compete and trade-secret Q&As.

  Primary sources to locate
    (a) Illinois's restrictive-covenant statute as amended effective 2022, including definitions, earnings thresholds, consideration requirements, notice/review requirements, legitimate-business-interest factors, reformation factors, and fee-shifting. [AUTHORITY TO FIND]
    (b) Illinois Supreme Court decisions establishing the legitimate-business-interest totality-of-circumstances test and the continued-employment-as-consideration rule, and appellate decisions applying them to sales employees and customer relationships. [AUTHORITY TO FIND]
    (c) Illinois trade-secret statute and cases on customer lists and pricing as trade secrets. [AUTHORITY TO FIND]
    (d) Illinois tortious-interference elements and competitor's-privilege cases. [AUTHORITY TO FIND]
    (e) Illinois duty-of-loyalty / pre-departure solicitation cases. [AUTHORITY TO FIND]
    (f) Illinois injunction standards and procedure. [AUTHORITY TO FIND]
    (g) Any post-2022 appellate decisions interpreting the amended statute, particularly on the earnings definition and the "non-compete vs. non-solicit" classification. [AUTHORITY TO FIND]

  Suggested search terms (adapt to each platform's syntax)
    Statutory enforceability:
      "non-compete" /s "earnings" /s threshold & Illinois
      "covenant not to compete" /p void /p "annualized"
      "non-solicitation" /s "earnings" & Illinois
      "14 days" /p "consult" /p attorney /p covenant
      "adequate consideration" /p "continued employment" /p "two years"
    Reasonableness:
      "legitimate business interest" /p "totality of the circumstances"
      "near-permanent" /p customer /p covenant
      "blue pencil" OR reformation /p "restrictive covenant" & Illinois
      "100 miles" OR "geographic" /p overbroad /p "non-compete" & Illinois
    Trade secrets:
      "customer list" /p "trade secret" /p "reasonable measures" & Illinois
      pricing /p "trade secret" /p "generally known" & Illinois
      "inevitable disclosure" & Illinois
    Tort / loyalty:
      "tortious interference" /p "prospective economic advantage" /p elements & Illinois
      "competitor's privilege" OR "competition privilege" & Illinois
      "duty of loyalty" /p solicit /p "prior to resignation"
    Remedies / exposure:
      "preliminary injunction" /p "restrictive covenant" /p "irreparable harm" & Illinois
      "attorney's fees" /p employee /p prevail /p "non-compete" & Illinois
      "attorney general" /p "restrictive covenant" /p enforcement & Illinois

  Suggested sequence
    1. Pin down the agreement date and total earnings. If earnings are below the statutory non-compete threshold, the non-compete claim likely fails at the threshold; research then centers on any non-solicit/confidentiality language, trade-secret, and tort theories.
    2. Confirm formation requirements (review period, counsel advisement, consideration).
    3. Only then invest in reasonableness/reformation analysis.
    4. In parallel, assess trade-secret and interference claims, which may be the client's strongest route to stopping customer contact regardless of the covenant.
    5. Evaluate fee-shifting exposure before recommending suit; consider a cease-and-desist letter as a first step with the exposure analysis in hand.

Reminder: all thresholds, time periods, elements, and factors stated above are general descriptions and must be verified against current primary Illinois authority by a licensed attorney before any advice is given.

