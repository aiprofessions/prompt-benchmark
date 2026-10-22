# Transcript — law-en-research-memo-01 — gpt-6-astra — run 1

- model_id: `gpt-6-astra` (provider `openai`)
- started_utc: 2026-10-19T11:40:52+00:00
- duration_s: 67.4
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

Preliminary assessment

The earnings requirement may be dispositive. Illinois generally prohibits a non-compete entered in 2022 for an employee whose annualized earnings did not exceed $75,000. Base salary of $48,000 suggests a serious enforceability problem, but the relevant earnings measure may include commissions, bonuses, and other compensation. The signing date, statutory earnings definition, and applicable measurement period must be checked. [AUTHORITY TO FIND]

Employment with a competitor 30 miles away and contact with café customers do not, by themselves, establish an enforceable claim. A separate customer nonsolicitation obligation or misuse of confidential information could change the analysis.

Every point below must be verified in primary sources by a licensed attorney.

1. Legal issues and elements or factors

A. Is the non-compete eligible for enforcement under the Illinois rules applicable to a 2022 agreement?

The bakery would need to establish:

  • R. Example’s annualized earnings exceeded the applicable non-compete threshold. Determine total qualifying earnings rather than relying solely on base salary.
  • The bakery provided the required written advice to consult an attorney and the required opportunity to review the agreement, generally at least 14 calendar days. Voluntary signing sooner does not necessarily defeat compliance.
  • Adequate consideration supported the promise. Generally, two years of employment after signing can supply consideration; other professional or financial benefits may also qualify. Employment from 2022 to August 2026 appears to satisfy the duration route, subject to exact dates.
  • Any applicable exclusions, exceptions, amendments, and effective-date rules were satisfied. [AUTHORITY TO FIND]

Adequate consideration does not cure a failure to meet an independent earnings or notice requirement. [AUTHORITY TO FIND]

B. Is this restriction reasonable and necessary to protect a legitimate business interest?

The bakery generally would need to show a valid employment-related covenant that:

  • Is no broader than necessary to protect a legitimate business interest.
  • Does not impose undue hardship on R. Example.
  • Does not injure the public.

Relevant factors include the employee’s customer relationships and influence, access to confidential information, the duration and stability of customer relationships, and the restriction’s time, territory, and activity scope. Ordinary competition alone is not enough. [AUTHORITY TO FIND]

Here, “any baked-goods sales” could reach work unrelated to his former duties or customers. The bakery needs evidence explaining why two years and 100 miles match its actual business interests rather than simply excluding competition. Thirty miles may fall within the covenant, but the agreement’s geographic reference point and measurement method matter. [AUTHORITY TO FIND]

C. If enforceable, has R. Example breached the agreement, and may a court narrow it?

The bakery would need to establish a valid contract, its own required performance, conduct within the prohibited scope, and a basis for the requested remedy. The actual contractual language controls whether his current sales activities constitute breach. [AUTHORITY TO FIND]

If narrowing is requested, relevant considerations may include the original restriction’s fairness, the bakery’s good faith, the extent of rewriting required, and any severability or modification language. Do not assume a court will narrow the restriction or that narrowing can rescue a covenant prohibited by an earnings requirement. [AUTHORITY TO FIND]

D. Is there a separate, enforceable customer nonsolicitation obligation?

If the signed documents contain one, the bakery would need to establish its statutory eligibility, consideration, procedural compliance, reasonable customer scope, and breach. Illinois generally applied a lower earnings threshold—earnings exceeding $45,000—to nonsolicitation agreements entered in 2022. The $48,000 base salary may satisfy that threshold, but not the other requirements. [AUTHORITY TO FIND]

Determine whether the clause prohibits solicitation, accepting business, or both; which customers it covers; and whether R. Example initiated the contacts. A nonsolicitation promise cannot simply be assumed from the non-compete. [AUTHORITY TO FIND]

E. Are there independent confidentiality, trade-secret, or interference claims?

Potential claims require evidence beyond customer contact:

  • Confidentiality breach: a valid obligation, covered information, and prohibited use or disclosure.
  • Trade-secret misappropriation: specifically identified information with economic value from secrecy, reasonable secrecy protections, and improper acquisition, use, or disclosure. Customer identities are not automatically trade secrets.
  • Contract interference: an enforceable customer contract, knowledge, intentional unjustified inducement of breach, actual breach, and resulting damage.
  • Business-expectancy interference: a sufficiently concrete expected relationship, knowledge, intentional unjustified interference preventing its realization, and damage. Lawful competitive conduct and applicable privileges must be assessed. [AUTHORITY TO FIND]

F. Can the bakery obtain prompt injunctive relief, and what are the risks?

For preliminary relief, the bakery generally must establish a clearly ascertainable right requiring protection, irreparable harm, no adequate legal remedy, and a likelihood of success on the merits. Counsel must also assess equitable balancing, public interests, procedural requirements, and security or bond. An emergency request needs evidence of imminent injury, not merely competition or speculative lost sales. [AUTHORITY TO FIND]

Research the employee’s potential recovery of attorney fees and costs if he prevails in an employer enforcement action, as well as exposure from an improperly issued injunction. [AUTHORITY TO FIND]

2. Facts and documents still needed

  • Every signed agreement, attachment, amendment, offer letter, compensation plan, and incorporated policy; choice-of-law, forum, arbitration, confidentiality, nonsolicitation, severability, and tolling terms.
  • Exact offer, delivery, signing, start, amendment, and resignation dates; written attorney-consultation advice and review-period records.
  • Payroll, commission, bonus, and benefit records needed to calculate qualifying earnings for the legally relevant period.
  • His actual duties, territory, customer assignments, training, and access to pricing, margins, recipes, customer preferences, or sales strategy.
  • The bakery’s actual service area and reasons for selecting two years, 100 miles, and all baked-goods sales.
  • The competitor’s location, his work locations and duties, and the covenant’s radius reference point.
  • Specific café contacts: who initiated them, dates, messages, offers, resulting orders, lost accounts, and available witnesses.
  • Customer contracts, termination rights, purchasing history, expected future orders, and evidence distinguishing lost profits from ordinary customer turnover.
  • Any downloads, forwarded emails, retained files, or unusual access; secrecy controls and lawful preservation of relevant records.
  • When the bakery learned of the conduct, any delay or consent, and the precise relief it wants.

3. Research plan

Primary sources and databases

  • Official Illinois legislative materials: restrictive-covenant provisions as effective in 2022, historical amendments, earnings definitions, notice, consideration, reformation, and fee shifting. Check whether later amendments or renewed agreements affect the analysis. [AUTHORITY TO FIND]
  • Official Illinois judicial opinions and Westlaw, Lexis, or Bloomberg Law: controlling Illinois Supreme Court decisions, relevant appellate decisions, and subsequent treatment. Distinguish pre-2022 decisions from decisions applying the newer statutory framework. [AUTHORITY TO FIND]
  • Official Illinois court rules, civil-procedure materials, and local circuit rules: temporary restraining orders, preliminary injunctions, verified filings, notice, security, and expedited discovery. [AUTHORITY TO FIND]
  • Official Illinois trade-secret materials and controlling decisions addressing confidentiality and interference. Use federal decisions applying Illinois law as persuasive authority only, with their status identified. [AUTHORITY TO FIND]
  • Relevant court dockets for procedural examples; validate all substantive propositions against primary authority and citator results.

Suggested searches

  • Illinois noncompete 2022 annualized earnings commissions bonuses threshold
  • Illinois restrictive covenant written attorney advice fourteen days
  • Illinois noncompete adequate consideration two years employment
  • Illinois bakery sales noncompete legitimate business interest customer relationships
  • Illinois noncompete all sales activity geographic scope undue hardship
  • Illinois restrictive covenant reformation earnings threshold void
  • Illinois customer nonsolicitation solicitation accepting business
  • Illinois customer list trade secret reasonable secrecy measures
  • Illinois competitor privilege customer business expectancy interference
  • Illinois preliminary injunction noncompete irreparable harm lost customers
  • Illinois employee prevailing attorney fees restrictive covenant

Prioritize statutory eligibility before expensive emergency litigation. If the earnings bar defeats the non-compete, investigate only independently supported obligations or misconduct—not customer contact alone. [AUTHORITY TO FIND]

