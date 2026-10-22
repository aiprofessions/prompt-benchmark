# Transcript — law-en-research-memo-01 — gemini-4-argon-medium — run 1

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:19:26+00:00
- duration_s: 47.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: dc4abdb0c63d00c579093230345e61dec8ac0d18e390129631dbcb1cff1166e3
- agy_usage: {"input_tokens": 829, "output_tokens": 3629, "thinking_tokens": 211, "cache_read_tokens": 0, "total_tokens": 4458}
- agy_num_turns: 1
- agy_tool_calls: 0 (transcript steps 2)

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

**DISCLAIMER:** Every point, legal standard, threshold, and element outlined below is preliminary and **must be verified in primary sources by a licensed attorney**. No specific cases, statutes, or citations are named in this outline; all references to governing law are marked as **[AUTHORITY TO FIND]**.

---

### (1) Legal Issues (Framed as Questions)

1. **Statutory Compensation Thresholds (Non-Compete vs. Non-Solicitation):** Under Illinois statutory law governing restrictive covenants in effect for agreements entered into in 2022 **[AUTHORITY TO FIND]**, is the restrictive covenant void and unenforceable *ab initio* because the former employee’s annualized earnings ($48,000 base salary) fell below the statutory minimum earnings threshold required for a covenant not to compete (or, if severable/applicable, a covenant not to solicit)?
2. **Statutory Procedural Prerequisites (Notice and Review Period):** Under Illinois statutory law **[AUTHORITY TO FIND]**, did the employer comply with mandatory pre-execution procedural requirements—specifically, advising the employee in writing to consult with an attorney and providing the required minimum number of calendar days (or advance notice prior to the start of employment) to review the covenant before signing?
3. **Adequacy of Consideration:** Under Illinois statutory and common law **[AUTHORITY TO FIND]**, was the restrictive covenant supported by adequate consideration given that the employee was hired in 2022 and resigned in August 2026 (approximately four years of continued employment)?
4. **Legitimate Business Interest & Common-Law Reasonableness:** Under Illinois statutory and totality-of-the-circumstances common law **[AUTHORITY TO FIND]**, is a two-year, 100-mile restriction covering "any baked-goods sales" no greater than required to protect a legitimate business interest of the wholesale bakery, or is it unenforceable as overbroad?
5. **Judicial Modification ("Blue-Penciling") or Severability:** If the broad non-compete is overbroad or statutorily barred, can and will an Illinois court reform or modify the covenant **[AUTHORITY TO FIND]** (or enforce a separate customer non-solicitation clause, if one exists in the agreement) to solely prohibit the former employee from soliciting the client’s existing café customers?
6. **Alternative Causes of Action (Trade Secrets / Tortious Interference):** If the restrictive covenant is unenforceable, can the client stop the former employee from contacting its café customers under Illinois trade secret law **[AUTHORITY TO FIND]** or common-law claims (such as tortious interference with business expectancy or breach of fiduciary duty)?
7. **Standards for Preliminary Injunctive Relief and Risk of Fee-Shifting:** Does the client satisfy the Illinois elements for a temporary restraining order (TRO) or preliminary injunction **[AUTHORITY TO FIND]**, and what is the client's exposure to mandatory prevailing-employee attorney’s fees and costs under Illinois statute **[AUTHORITY TO FIND]** if enforcement fails?

---

### (2) Elements or Factors the Client Must Establish (Per Issue)

#### Issue 1: Statutory Compensation Thresholds **[AUTHORITY TO FIND]**
To overcome statutory income bars in Illinois for agreements signed in 2022, the client must establish:
* **Qualifying "Annualized Rate of Earnings":** That the employee’s total annualized rate of earnings (which under statutory definitions **[AUTHORITY TO FIND]** may include base salary plus commissions, bonuses, or other taxable compensation reflected on W-2 forms) exceeded the statutory dollar floor in effect in 2022 for a **covenant not to compete** (generally understood to be $75,000/year for 2022 agreements, subject to verification in **[AUTHORITY TO FIND]**).
* **Non-Solicitation Threshold (if applicable):** If the agreement contains a separate customer non-solicitation restriction (or could be construed as one), that the employee’s annualized rate of earnings exceeded the lower statutory dollar floor for a **covenant not to solicit** (generally understood to be $45,000/year for 2022 agreements, subject to verification in **[AUTHORITY TO FIND]**).

#### Issue 2: Statutory Procedural Prerequisites **[AUTHORITY TO FIND]**
To establish that the agreement is not void for procedural non-compliance, the client must prove:
* **Written Advisement:** The employer advised the employee *in writing* to consult with an attorney before entering into the covenant.
* **Advance Review Period:** The employer provided the employee with a copy of the covenant at least the statutorily required number of calendar days (generally understood to be 14 calendar days, subject to verification in **[AUTHORITY TO FIND]**) before the commencement of employment, or provided at least that many calendar days to review the covenant (unless the employee voluntarily and knowingly waived the remainder of the review period in writing, if permitted by **[AUTHORITY TO FIND]**).

#### Issue 3: Adequacy of Consideration **[AUTHORITY TO FIND]**
The client must establish one of the following under Illinois statutory rules **[AUTHORITY TO FIND]**:
* **Duration of Employment:** The employee worked for the employer for a period of at least two years after signing the agreement (here, 2022 to August 2026 appears to satisfy this element); **OR**
* **Other Adequate Consideration:** The employer provided professional or financial benefits adequate by themselves (or in combination with the period of employment) to support the restriction.

#### Issue 4: Legitimate Business Interest & Three-Prong Reasonableness **[AUTHORITY TO FIND]**
Under Illinois statutory codification of the common-law three-prong test **[AUTHORITY TO FIND]**, the client must prove that the restraint:
1. **Is no greater than required for the protection of a legitimate business interest of the employer**, evaluated under the totality of the circumstances, including:
   * Near-permanence of customer relationships in the wholesale bakery/café industry;
   * The employee's acquisition, through his employment, of confidential information (e.g., pricing margins, custom recipes, delivery schedules, café buyer preferences) that he is attempting to use for his own benefit; and
   * Time and place restrictions.
2. **Does not impose undue hardship on the employee** (e.g., ability to earn a livelihood).
3. **Is not injurious to the public** (e.g., impact on market competition in the relevant area).
* *Specific Scope Factors:* The client must justify why a **2-year duration**, a **100-mile radius**, and an activity bar covering **"any baked-goods sales"** (even to non-customers or in different market segments) are narrowly tailored to its actual market area and customer base **[AUTHORITY TO FIND]**.

#### Issue 5: Judicial Modification ("Blue-Penciling") or Severability **[AUTHORITY TO FIND]**
To persuade an Illinois court to partially enforce or modify an overbroad agreement **[AUTHORITY TO FIND]**, the client must establish:
* **Fairness of Original Restraint:** The original restraint was drafted in good faith and was not so extensively overreaching as to be unconscionable or against public policy.
* **Statutory Factors for Reformation:** Under Illinois statutory standards **[AUTHORITY TO FIND]**, courts consider factors such as the fairness of the restraints as originally written, whether the original restriction reflects a good-faith effort to protect a legitimate business interest, the extent of such reformation, and whether the parties included a severability or modification clause in the contract. *(Note: Verify in **[AUTHORITY TO FIND]** whether a covenant void for failing the statutory wage threshold can be reformed at all, as opposed to being entirely void).*

#### Issue 6: Alternative Causes of Action **[AUTHORITY TO FIND]**
* **Misappropriation of Trade Secrets:** The client must establish (1) the existence of a trade secret (information that is sufficiently secret to derive economic value, not generally known in the wholesale bakery industry, and subject to reasonable efforts to maintain its secrecy—note that mere customer identities known in the trade often do not qualify **[AUTHORITY TO FIND]**); (2) misappropriation (improper acquisition, disclosure, or use); and (3) damages or threatened irreparable harm.
* **Tortious Interference with Prospective Economic Advantage / Contract:** The client must establish (1) a valid business relationship or reasonable expectancy of entering into/continuing a valid business relationship with the cafés; (2) the former employee's knowledge of the expectancy; (3) intentional and unjustified interference inducing or causing a breach or termination of the expectancy (exceeding lawful competition **[AUTHORITY TO FIND]**); and (4) damages.

#### Issue 7: Preliminary Injunctive Relief & Fee-Shifting Risk **[AUTHORITY TO FIND]**
* **Injunctive Relief Elements:** (1) A clearly ascertainable right in need of protection; (2) irreparable harm in the absence of an injunction; (3) no adequate remedy at law; and (4) a likelihood of success on the merits **[AUTHORITY TO FIND]**.
* **Statutory Fee-Shifting Risk:** Under Illinois statute **[AUTHORITY TO FIND]**, if an employer files a civil action to enforce a covenant not to compete or a covenant not to solicit and the **employee prevails**, the employee is generally entitled to recover all costs and all reasonable attorney’s fees regarding such claim from the employer (subject to verification in **[AUTHORITY TO FIND]**).

---

### (3) Facts Still Needed from the Client

1. **The Complete Employment Agreement & Onboarding Documents:**
   * Exact text of the 2022 agreement: Does it contain a separate **customer non-solicitation clause** and/or **confidentiality clause** in addition to the non-compete? Does it contain a severability or modification clause?
   * Exact date the agreement was signed in 2022 (to confirm whether it was signed on or after the effective date of the 2022 statutory amendments **[AUTHORITY TO FIND]**).
   * Written proof of pre-signing notice: Did the agreement or offer letter explicitly advise R. Example in writing to consult an attorney? How many days before his start date (or before signing) was the agreement provided to him?
2. **Complete Compensation Records (2022–2026):**
   * Beyond the $48,000 base salary, did R. Example earn **sales commissions, bonuses, or other compensation**?
   * What were his total annualized earnings on his W-2s (or projected annualized rate at hiring in 2022 and through 2026)? Did his total compensation reach or exceed the statutory threshold for a non-compete (or at least the lower threshold for a non-solicitation clause) **[AUTHORITY TO FIND]**?
3. **Scope of the Client’s Business and Market Area:**
   * Where does Sample Bakery LLC actually sell and deliver its wholesale baked goods? Does its territory extend 100 miles, or is it localized?
   * What types of baked goods does Sample Bakery sell, and how does the competitor's product line compare?
4. **Customer Relationships & Alleged Solicitation:**
   * How long has Sample Bakery done business with the targeted café customers? Are those cafés under exclusive contracts, or do they buy from multiple wholesale bakeries simultaneously (spot-market / non-exclusive)?
   * Which specific café customers did R. Example personally service while employed by Sample Bakery, and is he only contacting those specific cafés or others?
   * Have any cafés actually stopped buying from Sample Bakery or reduced their orders since August 2026?
5. **Confidential Information & Exit Circumstances:**
   * Did R. Example take any physical or electronic documents (customer lists, pricing sheets, cost margins, recipes, order histories) before resigning in August 2026?
   * What security measures (password protection, restricted access, confidentiality agreements) did Sample Bakery use to protect its customer and pricing data?

---

### (4) Research Plan

#### A. Primary Sources and Databases to Search
1. **Illinois Compiled Statutes (via Westlaw, Lexis+, or the official Illinois General Assembly website):**
   * Locate the Illinois chapter and act governing employment restrictive covenants, specifically the statutory amendments effective January 1, 2022 **[AUTHORITY TO FIND]**.
   * Locate the Illinois statute governing trade secrets **[AUTHORITY TO FIND]**.
2. **Illinois Supreme Court and Illinois Appellate Court Decisions (via Westlaw or Lexis+):**
   * Search for decisions from 2022 to the present interpreting the 2022 statutory amendments (especially regarding calculation of "annualized rate of earnings," strict compliance with the 14-day notice and attorney-consultation requirements, and whether a court can sever/enforce a non-solicitation obligation when the employee earns between the non-solicitation threshold and the non-compete threshold) **[AUTHORITY TO FIND]**.
   * Search for foundational Illinois Supreme Court decisions on the three-prong reasonableness test and the "legitimate business interest" totality-of-the-circumstances test **[AUTHORITY TO FIND]**.
3. **Federal District Court Decisions in Illinois (Northern, Central, and Southern Districts of Illinois) & Seventh Circuit Decisions (via Westlaw or Lexis+):**
   * Because few post-2022 state appellate opinions may yet have addressed every nuance of the 2022 statutory thresholds and notice rules, federal district court opinions applying Illinois law on motions to dismiss or motions for preliminary injunction are critical persuasive resources **[AUTHORITY TO FIND]**.
4. **Illinois Attorney General Enforcement Materials:**
   * Check for any statutory investigation/enforcement guidance issued by the Illinois Attorney General regarding unlawful restrictive covenants **[AUTHORITY TO FIND]**.

#### B. Suggested Search Terms (Boolean / Terms & Connectors)

* **Statutory Thresholds, Notice Requirements, & Post-2022 Enforcement:**
  * `("covenant not to compete" OR "covenant not to solicit" OR "non-compete" OR "restrictive covenant") /p ("annualized rate of earnings" OR "75,000" OR "45,000")`
  * `("covenant not to compete" OR "restrictive covenant") /p ("14 calendar days" OR "consult with an attorney" OR "advise the employee in writing")`
  * `("covenant not to compete" OR "covenant not to solicit") /p ("prevailing" OR "attorney's fees" OR "attorneys' fees" OR "costs")`
* **Legitimate Business Interest & Geographic/Activity Overbreadth (Wholesale / Food / Sales):**
  * `("non-compete" OR "restrictive covenant") /p "legitimate business interest" /p ("near-permanent" OR "confidential information") /p ("wholesale" OR "bakery" OR "food" OR "sales")`
  * `("non-compete" OR "restrictive covenant") /p ("100 miles" OR "100-mile" OR "radius") /p ("overbroad" OR "unreasonable" OR "modify" OR "blue pencil" OR "reformation")`
  * `("any capacity" OR "any sales") /p ("non-compete" OR "restrictive covenant") /p ("overbroad" OR "unreasonable")`
* **Severability / Blue-Penciling Between Non-Compete and Non-Solicitation:**
  * `("reformation" OR "blue-pencil" OR "severability" OR "modify") /p ("covenant not to compete" OR "non-compete") /p ("solicit" OR "non-solicitation")`
* **Trade Secret Status of Customer Lists in Illinois:**
  * `"trade secret" /p ("customer list" OR "pricing") /p ("wholesale" OR "food" OR "distributor" OR "bakery")`

---
*Reminder: Every legal principle, statutory requirement, and threshold referenced above must be independently verified in primary Illinois legal sources by a licensed attorney before advising the client or initiating litigation.*
