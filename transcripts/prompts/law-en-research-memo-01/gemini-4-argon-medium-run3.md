# Transcript — law-en-research-memo-01 — gemini-4-argon-medium — run 3

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:44:00+00:00
- duration_s: 43.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: dc4abdb0c63d00c579093230345e61dec8ac0d18e390129631dbcb1cff1166e3
- agy_usage: {"input_tokens": 829, "output_tokens": 2798, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 3627}
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

**DISCLAIMER:** *Every point outlined below is for preliminary research orientation only and must be verified in primary sources by a licensed attorney.*

---

### (1) Legal Issues (Framed as Questions)

1. **Statutory Compliance (Income Thresholds & Procedural Requirements):** Under Illinois statutes governing restrictive covenants enacted or effective in 2022 [AUTHORITY TO FIND], is a non-compete agreement enforceable against an employee who signed in 2022 with a base salary of $48,000, and did the employer satisfy mandatory statutory notice and review-period requirements at the time of hiring?
2. **Enforceability of the Covenant (Common Law & Statutory Reasonableness):** Assuming statutory prerequisites are met, is a two-year, 100-mile radius restriction barring "any baked-goods sales" supported by adequate consideration and reasonably tailored to protect a legitimate business interest of Sample Bakery LLC [AUTHORITY TO FIND]?
3. **Severability / Judicial Modification ("Blue-Penciling"):** If the non-compete provision is unenforceable due to the income threshold or overbreadth, does the agreement contain a separate, enforceable non-solicitation covenant (which may be subject to a lower statutory earnings threshold), or will an Illinois court modify/reform the agreement to limit the former employee from soliciting the client's café customers [AUTHORITY TO FIND]?
4. **Alternative Claims (Trade Secrets / Tortious Interference):** Outside of the restrictive covenant, does the former employee’s outreach to the client's café customers constitute misappropriation of trade secrets under Illinois trade secret law [AUTHORITY TO FIND] or tortious interference with existing or prospective business relations [AUTHORITY TO FIND]?
5. **Availability of Injunctive Relief:** Can Sample Bakery LLC satisfy the standard for a temporary restraining order (TRO) or preliminary injunction in Illinois state court to immediately halt the former employee's competitive sales or customer solicitation [AUTHORITY TO FIND]?

---

### (2) Elements or Factors to Establish (As Generally Understood)

*(Note: Every point below must be verified in primary sources by a licensed attorney.)*

#### Issue 1: Statutory Compliance (Income Thresholds & Procedural Prerequisites)
To survive threshold statutory bars in Illinois for agreements entered into in or after 2022 [AUTHORITY TO FIND], the employer generally must establish:
* **Earnings Threshold:** The employee’s actual or annualized expected earnings (which may include base salary plus commissions, bonuses, or other statutory inclusions [AUTHORITY TO FIND]) exceeded the statutory minimum dollar threshold required for a covenant not to compete (or the potentially lower statutory threshold required for a covenant not to solicit) [AUTHORITY TO FIND]. *(Note: A $48,000 base salary strongly implicates statutory minimum wage/salary bans in Illinois unless total compensation or specific statutory exceptions apply).*
* **Pre-Signing Notice:** The employer advised the employee in writing to consult with an attorney before signing the covenant [AUTHORITY TO FIND].
* **Review Period:** The employer provided the employee with a copy of the covenant at least the statutorily required number of calendar days (generally 14 days) before employment began or before the agreement needed to be signed [AUTHORITY TO FIND].

#### Issue 2: Enforceability of the Covenant (Reasonableness & Consideration)
Under Illinois law [AUTHORITY TO FIND], to enforce a post-employment restrictive covenant, the employer must establish:
* **Ancillarity and Consideration:** The covenant is ancillary to a valid employment relationship and supported by adequate consideration (under Illinois law, continued at-will employment for a substantial period—often analyzed around a two-year benchmark, here 2022 to 2026—or additional benefits/statutory equivalents) [AUTHORITY TO FIND].
* **Legitimate Business Interest:** Based on the totality of the circumstances [AUTHORITY TO FIND], the employer has a protectable interest, evaluated through factors such as:
  * Near-permanence of customer relationships;
  * The employee’s acquisition of confidential information through employment; and
  *Whether the employee would not have had contact with the customers but for his employment with the client.
* **Reasonable Scope (Three-Prong Test):** The restriction is no greater than required for the protection of the legitimate business interest, specifically regarding:
  * **Duration:** Two years is reasonable in this specific industry context;
  * **Geographic Area:** A 100-mile radius is coextensive with the area where the client actually conducts business or where the employee operated; and
  * **Scope of Activity:** Banning "any baked-goods sales" (often called a blanket industry ban) is not impermissibly overbroad compared to restricting only sales of competing wholesale products or sales to specific customers [AUTHORITY TO FIND].
* **No Undue Hardship or Public Injury:** The restriction does not impose an undue hardship on the employee's ability to earn a livelihood and is not injurious to the public [AUTHORITY TO FIND].

#### Issue 3: Judicial Modification / Non-Solicitation Distinction
To persuade an Illinois court to narrow an overbroad covenant or enforce a subset of it [AUTHORITY TO FIND], the client must establish:
* **Distinction Between Non-Compete and Non-Solicit:** Whether a distinct non-solicitation clause exists in the contract that survives under a lower statutory earnings threshold [AUTHORITY TO FIND].
* **Factors for Modification:** That the original restraint was drafted in good faith, is not severely unfair as written, and requires only minor modification rather than a complete judicial rewrite of the parties' agreement, along with the presence of a severability/modification clause in the contract [AUTHORITY TO FIND].

#### Issue 4: Alternative Claims (Trade Secrets / Tortious Interference)
If the covenant is void, the client would need to establish:
* **Trade Secret Misappropriation [AUTHORITY TO FIND]:**
  * The café customer information (e.g., pricing, margins, specific preferences, non-public contact persons) qualifies as a trade secret (secret, derives economic value from not being generally known, and is subject to reasonable efforts to maintain secrecy);
  * The former employee misappropriated it through improper acquisition, disclosure, or use.
* **Tortious Interference with Business Expectancy / Contract [AUTHORITY TO FIND]:**
  * Existence of a valid contract or reasonable expectancy of entering into/continuing a valid business relationship with the cafés;
  * The employee's knowledge of the expectancy/contract;
  * Intentional and unjustified interference inducing or causing a breach or termination (beyond lawful competition); and
  * Damages resulting to the client.

#### Issue 5: Preliminary Injunctive Relief
To obtain an injunction stopping the employee in Illinois state court [AUTHORITY TO FIND], the client must establish:
* **Clearly Ascertainable Right:** A clearly ascertainable right in need of protection;
* **Irreparable Harm:** The client will suffer irreparable injury without the injunction (e.g., permanent loss of customer goodwill/relationships);
* **Inadequate Remedy at Law:** Monetary damages cannot adequately compensate for the harm; and
* **Likelihood of Success on the Merits:** A fair question as to the likelihood of succeeding on the underlying claims (and that the balance of hardships favors the client).

---

### (3) Facts Still Needed from the Client

1. **The Agreement & Onboarding Process:**
   * What is the exact date in 2022 when the agreement was presented and signed?
   * Did the agreement include a separate **non-solicitation** clause and/or **confidentiality** clause in addition to the non-compete clause?
   * Does the agreement contain a severability or judicial modification clause?
   * Was R. Example given at least 14 calendar days to review the agreement before signing or starting work, and was he advised in writing to consult an attorney? Do we have written proof/acknowledgment of this?
2. **Total Compensation:**
   * Beyond the $48,000 base salary, did R. Example earn sales commissions, bonuses, or other compensation?
   * What were his total annualized W-2 earnings in 2022, 2023, 2024, 2025, and 2026?
3. **Nature of Customer Relationships & Confidential Information:**
   * Are the café customers publicly identifiable (e.g., any local bakery could look up cafés on a map and cold-call them), or did R. Example take non-public customer lists, pricing matrices, order histories, or custom recipes/specifications?
   * Did Sample Bakery have exclusive or long-term contracts with these cafés, or do the cafés buy baked goods from multiple vendors on an order-by-order basis?
   * What security measures does Sample Bakery use to protect customer data (passwords, restricted CRM access, confidentiality policies)?
4. **Geographic & Market Scope:**
   * What is Sample Bakery’s actual delivery and sales radius? Does it actually serve customers 100 miles away?
   * What specific territory or accounts was R. Example assigned to during his employment?
   * Does the competing bakery sell the exact same type of wholesale products, or different baked goods?
5. **Damages & Urgency:**
   * Have any café customers actually stopped buying from Sample Bakery or reduced their orders since August 2026?

---

### (4) Research Plan

*(Reminder: Every point and authority located through this plan must be verified in primary sources by a licensed attorney.)*

#### A. Primary Sources & Databases to Search
1. **Illinois Compiled Statutes (via Westlaw, Lexis+, or the official Illinois General Assembly database):**
   * Search the Labor and Employment chapters specifically for the Illinois statutory framework governing freedom to work and restrictive covenants (specifically looking at the amendments that took effect in 2022) [AUTHORITY TO FIND].
   * Search the Commercial/Trade chapters for the Illinois trade secrets statute [AUTHORITY TO FIND].
   * Search the Civil Procedure chapters for standards governing temporary restraining orders and preliminary injunctions [AUTHORITY TO FIND].
2. **Illinois Case Law (via Westlaw or Lexis+ — Illinois Supreme Court and Illinois Appellate Court databases):**
   * Locate the leading Illinois Supreme Court decisions establishing the "totality of the circumstances" test for legitimate business interests [AUTHORITY TO FIND].
   * Locate Illinois Appellate Court decisions post-2022 interpreting the statutory earnings thresholds, notice requirements, and how "annualized earnings" are calculated (specifically whether commissions count toward the threshold) [AUTHORITY TO FIND].
   * Locate Illinois cases involving wholesale food/product distributors and sales representatives to see how courts treat publicly identifiable retail/café customers versus proprietary customer relationships [AUTHORITY TO FIND].
   * Locate Illinois cases discussing whether a court can enforce or reform a general non-compete into a customer non-solicitation restriction when statutory thresholds are at issue [AUTHORITY TO FIND].

#### B. Suggested Search Terms

* **For Statutory Thresholds, Notice, and 2022 Amendments:**
  * `"restrictive covenant" /p ("earnings" OR "salary" OR "compensation" OR "threshold") /p ("non-compete" OR "covenant not to compete" OR "non-solicit")`
  * `"covenant not to compete" /p ("14 days" OR "fourteen days" OR "attorney" OR "consult") /p ("notice" OR "advise")`
  * `"annualized" /s ("earnings" OR "rate") /p ("commission" OR "bonus") /p "covenant"`
* **For Legitimate Business Interest & Bakery/Wholesale Customer Lists:**
  * `"legitimate business interest" /p "totality of the circumstances" /p ("near-permanent" OR "near permanence" OR "confidential")`
  * `("non-compete" OR "restrictive covenant") /p ("salesperson" OR "sales representative") /p ("wholesale" OR "food" OR "bakery" OR "distributor" OR "customer list")`
  * `"customer" /s ("publicly" OR "ascertainable" OR "directory") /p ("legitimate business interest" OR "trade secret")`
* **For Scope of Activity ("Any Sales") & Judicial Modification:**
  * `("non-compete" OR "restrictive covenant") /p ("any capacity" OR "any sales" OR "blanket") /p ("overbroad" OR "unreasonable")`
  * `("modify" OR "blue pencil" OR "reform" OR "severability") /p ("covenant not to compete" OR "non-solicitation") /p ("good faith" OR "unfair")`
* **For Attorney's Fees Risk (Crucial Statutory Check):**
  * `"covenant not to compete" /p "prevailing" /s "employee" /p ("attorney fees" OR "attorney's fees" OR "costs")` *(Note: Crucial to verify whether Illinois statute mandates fee-shifting to the employee if the employer sues to enforce an invalid covenant and loses [AUTHORITY TO FIND]).*
