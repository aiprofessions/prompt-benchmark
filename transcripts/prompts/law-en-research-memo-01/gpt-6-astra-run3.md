# Transcript — law-en-research-memo-01 — gpt-6-astra — run 3

- model_id: `gpt-6-astra` (provider `openai`)
- started_utc: 2026-10-19T12:11:00+00:00
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

Preliminary research outline only. Every point below must be verified in primary sources by a licensed attorney. All legal propositions are provisional: [AUTHORITY TO FIND].

1. Is the 2022 non-compete enforceable given the employee’s earnings?

Elements or factors:
  Illinois restricts non-competes based on an employee’s annualized earnings when the agreement is entered into. For a covenant signed in 2022, the relevant earnings threshold appears to require earnings exceeding $75,000. The statutory definition of earnings, not base salary alone, controls. [AUTHORITY TO FIND]

  The client would need to establish qualifying earnings above the applicable threshold. If $48,000 was his entire qualifying annualized compensation, this likely prevents enforcement regardless of the competitor’s proximity or customer contacts. [AUTHORITY TO FIND]

Facts needed:
  Exact signing and employment-start dates; compensation agreement; commissions, bonuses, and other potentially qualifying compensation; payroll records; and any later amendments, replacement covenants, or promotions accompanied by new agreements.

2. Were the agreement’s formation and consideration requirements satisfied?

Elements or factors:
  Investigate whether the employer advised him in writing to consult an attorney and provided the required review opportunity—generally at least 14 calendar days, subject to rules allowing voluntary earlier signing. [AUTHORITY TO FIND]

  Adequate consideration generally requires at least two years of employment after signing or sufficient additional professional or financial benefits, alone or combined with employment. Employment from 2022 through August 2026 appears favorable on this issue, but does not cure other defects. [AUTHORITY TO FIND]

  The client must also establish a valid agreement ancillary to an employment relationship. [AUTHORITY TO FIND]

Facts needed:
  Complete signed agreement and incorporated documents; delivery and signing records; written attorney-consultation notice; actual employment dates and interruptions; additional benefits; and choice-of-law, forum, severability, and amendment provisions.

3. Is this restriction reasonably tailored to a legitimate business interest?

Elements or factors:
  The restriction generally must be no greater than necessary to protect a legitimate business interest, impose no undue hardship on the employee, and not injure the public. Relevant circumstances include customer relationships, employee customer exposure, confidential information, and the restriction’s duration, geography, and activity scope. Preventing ordinary competition alone is insufficient. [AUTHORITY TO FIND]

  Two years, 100 miles, and “any baked-goods sales” require separate scrutiny. The activity restriction may reach customers, products, or roles unrelated to his work. Working 30 miles away does not itself establish enforceability. [AUTHORITY TO FIND]

Facts needed:
  Radius measurement point; actual sales territory; employee responsibilities; customer relationship duration and acquisition costs; employee access to pricing, margins, and buying patterns; information-security practices; and how the restriction affects his ability to earn a living.

4. Has he breached an enforceable obligation, and could a court narrow the restriction?

Elements or factors:
  The client must establish an enforceable obligation, conduct within its scope, and the prerequisites for the requested remedy. Obtain the exact wording rather than relying on the agreement’s label. [AUTHORITY TO FIND]

  Judicial modification is discretionary. Research permissible narrowing, fairness, drafting good faith, and whether statutory invalidity can be cured at all; do not assume a court will rewrite the covenant. [AUTHORITY TO FIND]

Facts needed:
  New employer, work location, territory, products, duties, first competitive activity, specific customer communications, resulting sales, and any contractual tolling or reformation language.

5. Are there independent customer-solicitation, confidentiality, or misconduct claims?

Elements or factors:
  A separate non-solicitation covenant may have a different earnings threshold—apparently earnings exceeding $45,000 for a 2022 agreement—but still requires statutory and reasonableness analysis. Do not assume the non-compete contains such a covenant. [AUTHORITY TO FIND]

  A trade-secret claim generally requires specifically identified economically valuable secret information, reasonable secrecy measures, and misappropriation. Confidentiality claims require an applicable duty and prohibited use or disclosure. Customer contact alone establishes neither. [AUTHORITY TO FIND]

  Interference claims require the applicable contractual relationship or business expectancy, knowledge, actionable interference, causation, and damages, with competition privileges considered. Predeparture disloyal conduct may present a separate issue. [AUTHORITY TO FIND]

Facts needed:
  Other signed restrictions; customer contracts; who initiated contact; timing of solicitation; downloaded or retained files; personal-device transfers; secrecy measures; alleged false statements; diverted orders; and documented losses.

6. Can the client obtain prompt injunctive relief, and what are the risks?

Elements or factors:
  Research temporary restraining order and preliminary-injunction requirements: a protectable right, likelihood of success, irreparable injury, inadequate legal remedy, and applicable equitable balancing. Also verify notice, evidence, security, and procedural requirements. [AUTHORITY TO FIND]

  Consider delay, whether losses are measurable, the employee’s defenses, potential wrongful-injunction exposure, and employee fee-shifting rights if the employer unsuccessfully pursues covenant enforcement. [AUTHORITY TO FIND]

Facts needed:
  Urgent threatened losses; customer declarations; evidence preservation; prior enforcement practices; employer breaches; and the client’s litigation budget and ability to provide security.

Research plan

  Start with the earnings gate and execution requirements before investing in an injunction motion.

  Primary sources: official Illinois legislative text and historical versions effective at execution; Illinois Supreme Court and appellate opinions; Illinois civil-procedure provisions, Supreme Court rules, and local circuit-court rules. For independent information-misuse claims, examine applicable state and federal primary law. [AUTHORITY TO FIND]

  Databases: Illinois General Assembly and Illinois Courts websites; Westlaw, Lexis, or Bloomberg Law for historical materials, opinions, and citator checks. Use secondary sources only to locate primary authority.

  Suggested searches:
    Illinois 2022 noncompete annualized earnings commissions threshold
    Illinois restrictive covenant attorney notice 14 days consideration
    Illinois bakery sales noncompete customer relationships geographic scope
    Illinois restrictive covenant reformation statutory invalidity
    Illinois nonsolicitation 2022 earnings threshold
    Illinois customer list trade secret reasonable secrecy measures
    Illinois former employee solicitation competition privilege
    Illinois preliminary injunction noncompete irreparable harm security
    Illinois restrictive covenant prevailing employee attorney fees

  Confirm subsequent amendments, controlling appellate authority for the filing court, and current treatment of every authority. Preserve evidence now without accessing the former employee’s or competitor’s accounts without authorization.

