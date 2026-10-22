# Transcript — law-en-research-memo-01 — gemini-4-argon-medium — run 2

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:32:22+00:00
- duration_s: 57.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: dc4abdb0c63d00c579093230345e61dec8ac0d18e390129631dbcb1cff1166e3
- agy_usage: {"input_tokens": 829, "output_tokens": 2860, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 3689}
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

**DISCLAIMER:** The following analysis is for preliminary research orientation only. **Every point, element, threshold, and legal standard below must be verified in primary sources by a licensed attorney.**

---

### (1) Legal Issues Framed as Questions

1. **Statutory Enforceability (Compensation & Notice Thresholds):** Under Illinois law governing restrictive covenants entered into in 2022 [AUTHORITY TO FIND], is the non-compete agreement void as a matter of law based on R. Example’s annualized earnings ($48,000 base salary plus any additional compensation) or a failure to comply with mandatory pre-signing notice and review requirements?
2. **Common Law / Statutory Reasonableness of the Covenant:** Even if statutory thresholds are met, is a 2-year, 100-mile non-compete covering "any baked-goods sales" enforceable under Illinois law [AUTHORITY TO FIND], or is it overbroad in duration, geographic scope, or scope of prohibited activity relative to Sample Bakery LLC's legitimate business interests?
3. **Reformation ("Blue-Penciling"):** If the covenant is deemed overbroad (or if the non-compete fails but a severable non-solicitation provision exists), will an Illinois court exercise its discretion to modify or partially enforce the agreement to prohibit R. Example from soliciting the client's specific café customers [AUTHORITY TO FIND]?
4. **Alternative Claims (Trade Secrets & Tortious Interference):** Regardless of the contract's validity, does R. Example’s outreach to Sample Bakery LLC’s café customers constitute misappropriation of trade secrets under state trade secret law [AUTHORITY TO FIND] or tortious interference with existing or prospective business relations [AUTHORITY TO FIND]?
5. **Injunctive Relief:** Can Sample Bakery LLC satisfy the requirements for a temporary restraining order (TRO) or preliminary injunction in Illinois state court to immediately halt R. Example’s competitive activities or customer solicitation [AUTHORITY TO FIND]?

---

### (2) Elements or Factors the Client Would Need to Establish

*(Note: All elements and factors below represent general legal principles in Illinois that must be verified in primary sources by a licensed attorney.)*

#### Issue 1: Statutory Thresholds for Post-2021 Restrictive Covenants [AUTHORITY TO FIND]
To survive threshold statutory bars in Illinois for an agreement signed in 2022, the employer generally must establish:
* **Minimum Annualized Earnings:** The employee’s actual or expected annualized rate of earnings exceeded the statutory minimum dollar threshold in effect at the time for a covenant not to compete (or the separate, lower statutory threshold for a covenant not to solicit) [AUTHORITY TO FIND]. *(Note: A $48,000 base salary alone falls below typical statutory thresholds enacted in Illinois for 2022 agreements, making commission/bonus calculations critical).*
* **Procedural Notice & Review:** The employer advised the employee in writing to consult with an attorney before signing and provided the employee with a copy of the covenant at least a statutorily prescribed number of calendar days (generally 14 days) before employment began or before signing [AUTHORITY TO FIND].
* **Adequate Consideration:** The employee worked for the employer for at least 2 years after signing the agreement (satisfied here: 2022 to August 2026), or received other adequate financial or professional consideration [AUTHORITY TO FIND].

#### Issue 2: Reasonableness and Legitimate Business Interest [AUTHORITY TO FIND]
For a restrictive covenant to be enforceable, the employer must establish under the totality of the circumstances that the restraint is ancillary to a valid employment relationship and:
* **No Greater Than Required:** The restraint (2 years, 100 miles, any baked-goods sales) is no greater than is required for the protection of a **legitimate business interest** of the employer [AUTHORITY TO FIND].
  * *Factors for Legitimate Business Interest:* Near-permanence of customer relationships; the employee's acquisition of confidential information through employment; and time, place, and scope restrictions [AUTHORITY TO FIND].
* **No Undue Hardship:** The restraint does not impose undue hardship on the employee's ability to earn a livelihood [AUTHORITY TO FIND].
* **Public Injury:** The restraint is not injurious to the public [AUTHORITY TO FIND].

#### Issue 3: Judicial Modification / Reformation [AUTHORITY TO FIND]
To convince an Illinois court to modify ("blue-pencil") an overbroad covenant rather than void it entirely, the employer generally must show:
* **Fairness of Original Restraint:** The original restraint was drafted in good faith and was not so extensively overbroad as to be unconscionable or tantamount to writing a new contract [AUTHORITY TO FIND].
* **Severability/Modification Provision:** Whether the contract contains an express severability or modification clause [AUTHORITY TO FIND].
* **Degree of Modification Required:** How closely the requested narrower relief (e.g., barring solicitation of existing café customers rather than barring all baked-goods sales within 100 miles) aligns with the original language [AUTHORITY TO FIND].

#### Issue 4: Alternative Claims (Trade Secrets / Tortious Interference) [AUTHORITY TO FIND]
* **Trade Secret Misappropriation [AUTHORITY TO FIND]:**
  1. The information at issue (e.g., customer lists, pricing structures, buying habits) is a "trade secret"—meaning it is sufficiently secret to derive economic value, is not generally known in the industry, and is the subject of reasonable efforts to maintain its secrecy (note: mere café names and public contact info usually do not qualify).
  2. The former employee misappropriated the information through improper acquisition, disclosure, or use.
* **Tortious Interference with Contract / Prospective Economic Advantage [AUTHORITY TO FIND]:**
  1. Existence of a valid/enforceable contract with the café customers (or a reasonable expectancy of entering into/continuing a valid business relationship).
  2. The defendant’s knowledge of the contract or expectancy.
  3. Intentional and unjustified interference by the defendant that induced a breach or prevented the expectancy from ripening (passing the line from lawful competition to wrongful conduct).
  4. Damages resulting from the interference.

#### Issue 5: Preliminary Injunctive Relief [AUTHORITY TO FIND]
To stop the employee immediately via a TRO or preliminary injunction, the client must establish:
1. **Ascertainable Right:** A clearly ascertainable right in need of protection (e.g., valid covenant, near-permanent customer relationships, or trade secrets) [AUTHORITY TO FIND].
2. **Irreparable Harm:** Irreparable injury will occur without the injunction (e.g., ongoing loss of customer goodwill or competitive position).
3. **No Adequate Remedy at Law:** Money damages alone cannot adequately compensate the injury.
4. **Likelihood of Success on the Merits:** A fair question as to the likelihood of success on the merits of the underlying claims.
5. **Balance of Hardships:** The benefits of granting the injunction outweigh the injury to the defendant.

---

### (3) Facts Still Needed from the Client

1. **Total Compensation Details:**
   * Did R. Example earn commissions, bonuses, or other compensation on top of the $48,000 base salary?
   * What were R. Example’s exact annualized W-2 earnings in 2022 and in each subsequent year through August 2026?
2. **Contract Text & Execution Circumstances:**
   * What is the exact text of the agreement? Does it include a separate **non-solicitation** clause and/or **confidentiality/non-disclosure** clause in addition to the non-compete? Does it have a severability/modification clause and an attorneys' fees provision?
   * What was the exact date in 2022 when the agreement was presented, and the exact date it was signed?
   * Was R. Example given at least 14 calendar days to review the agreement before signing or starting work, and was he advised *in writing* to consult an attorney?
3. **Nature of the Business & Customer Relationships:**
   * What is Sample Bakery LLC's actual geographic market area? Does it sell to cafés across the entire 100-mile radius, or only within a smaller local area?
   * Are the café customers under exclusive, long-term supply contracts, or do they buy wholesale baked goods from multiple bakeries on an order-by-order basis?
   * Would R. Example have had contact with these cafés *but for* his employment with Sample Bakery LLC?
4. **Confidential Information & Conduct:**
   * Did R. Example take any physical or electronic documents, customer lists, non-public pricing sheets, recipes, or order histories before resigning?
   * What specific measures did Sample Bakery LLC take to keep its customer data and pricing secret (e.g., password protection, restricted access, confidentiality agreements)?
   * Which specific café customers has R. Example contacted, did he service them personally while at Sample Bakery LLC, and has the client lost any accounts or revenue yet?

---

### (4) Research Plan

*(Reminder: Every point uncovered through this research plan must be verified in primary sources by a licensed attorney.)*

#### A. Primary Sources to Search
1. **Illinois Compiled Statutes:**
   * Chapter governing Employment, specifically the Act governing freedom to work and restrictive covenants (including the major statutory amendments that took effect on January 1, 2022, establishing wage thresholds for non-competes and non-solicits, the 14-day notice rule, judicial reformation standards, and prevailing-party attorney fee shifting for employees) [AUTHORITY TO FIND].
   * Illinois Trade Secrets Act [AUTHORITY TO FIND].
   * Illinois Code of Civil Procedure sections governing Temporary Restraining Orders and Preliminary Injunctions [AUTHORITY TO FIND].
2. **Illinois Case Law (Supreme Court and Appellate Courts):**
   * Leading Illinois Supreme Court decision establishing the "totality of the circumstances" test for legitimate business interests [AUTHORITY TO FIND].
   * Illinois Appellate Court decisions analyzing geographic scope, activity scope ("any sales capacity"), and "near-permanence" of customer relationships in the wholesale food/beverage or route-sales context [AUTHORITY TO FIND].
   * Illinois state court (and persuasive federal court) decisions interpreting the post-2021 statutory amendments on annualized earnings calculations, notice requirements, and blue-penciling [AUTHORITY TO FIND].

#### B. Databases to Search
* **Westlaw / Lexis+:** Illinois Annotated Statutes, Illinois State Cases, and Illinois federal district/appellate cases applying Illinois law (for recent interpretations of the 2022 statutory rules).
* **Secondary Sources (to quickly locate primary authorities):**
  * *Illinois Institute for Continuing Legal Education (IICLE)* handbooks on Employment Law and Restrictive Covenants.
  * *Illinois Jurisprudence* or *Nichols Illinois Civil Practice* (for injunctive relief standards).
* **Docket Search (Westlaw Precision / Lexis CourtLink / Local Circuit Court Portals):** Search recent Illinois circuit court filings in the relevant county (e.g., Chancery Division) for recent TRO/preliminary injunction rulings under the 2022 restrictive covenant statutory framework.

#### C. Suggested Search Terms

* **Statutory Thresholds & 2022 Amendments:**
  * `("covenant not to compete" OR "covenant not to solicit" OR "non-compete") /p ("annualized rate of earnings" OR "75,000" OR "45,000")`
  * `("covenant not to compete" OR "non-compete") /p ("14 calendar days" OR "consult with an attorney") /p (void OR enforceable)`
  * `("prevailing" /s "employee") /p ("covenant not to compete" OR "restrictive covenant") /p ("attorney's fees" OR "attorneys' fees")` *(Crucial: to check the client's risk of paying the employee's legal fees if the suit fails under the statute).*

* **Legitimate Business Interest & Wholesale/Bakery Context:**
  * `"legitimate business interest" /p "totality of the circumstances" /p ("non-compete" OR "restrictive covenant") & (wholesale! OR bakery OR "food" OR "route" OR "sales")`
  * `"near-permanen!" /p customer! /p (wholesale! OR bakery OR restaurant! OR cafe! OR distribut!)`
  * `("100 miles" OR "100-mile") /p ("non-compete" OR "restrictive covenant") /p (overbroad OR reasonable)`
  * `("any capacity" OR "any sales") /p ("non-compete" OR "restrictive covenant") /p (overbroad OR unenforceable)`

* **Blue-Penciling / Reformation:**
  * `("blue pencil!" OR "blue-pencil!" OR reform! OR modify) /p ("covenant not to compete" OR "restrictive covenant") /p ("discretion" OR "unfair" OR "good faith")`

* **Trade Secrets (Customer Lists):**
  * `"customer list!" /p "trade secret!" /p (public! OR "readily ascertainable" OR "telephone directory" OR "internet") & (wholesale! OR sales)`
