### Day 0 – Practical Exercises (With Model Answers)

Use these to train your brain to think like a **7–8 year Workday financial systems person**.  
First try each question yourself, then read the model answer.

---

#### Exercise 1 – Translate JD to Skills (with Example)

**Task**  
Open the root `README.md` and look at the JD‑based sections. For each JD bullet, map:

- JD line → Concrete skill → Where in this plan you will learn it (Day X).

**Example mapping (partial, for you to extend):**

| **JD Line** | **Concrete Skill** | **Day in Plan** |
|------------|--------------------|-----------------|
| “Configure/Test/Implement configuration changes in Financial Systems” | Understand how a request becomes config, how to design test cases, and how to move changes through environments | Day 2, Day 5, Day 6 |
| “Design/Develop/Test/Implement modifications to Integration programs” | Understand integration patterns, EIB basics, and how to validate data through SQL/BI | Day 5, Day 4 |
| “Resolve any data-related issues found … a passion for data and concern for data integrity is key” | Root‑cause analysis of mismatches across Workday, data warehouse, and BI; documenting issues clearly | Day 0, Day 3, Day 4, Day 5, Day 6 |

**Model approach to this exercise**

- Don’t just copy; **rewrite each JD bullet** in “skill language”:
  - “Configure/Test/Implement…” → “I must know how to design changes, test them thoroughly, and safely move them into production.”
- This trains you to instantly convert job posts into **study topics**, which is exactly what seniors do.

---

#### Exercise 2 – Personal Learning Plan (with Example)

**Task**  
Decide your timeline (3, 4–5, or 6–7 days) and write a concrete plan.

**Example if you choose 3 intense days:**

- **Day A (Today)**: Full Day 0 + Day 1
  - Objective: Master the **role, big picture, and core Workday navigation/objects**.
- **Day B**: Day 2 + Day 3
  - Objective: Understand **financial processes** (P2P, O2C, Record to Report) and how **reporting/Prism/Accounting Center** support them.
- **Day C**: Day 4 + Day 5 + Day 6
  - Objective: Focus on **Adaptive, SQL, Power BI, integrations/EIBs**, and **project + interview prep**.

**Model answer pattern**

- A good plan includes:
  - **Time blocks** (e.g. “Morning = theory, Afternoon = exercises”).
  - **Output goals** (e.g. “By end of Day B I can explain how Accounting Center works.”).
- Seniors always think in **deliverables and outcomes**, not just “I will read stuff.”

---

#### Exercise 3 – Finance Refresh (with Sample Bullets)

**Task**  
Without leaving this repo, use `theory.md` as your main reference and write your own bullets.

**Model example (you should customize and extend):**

- **What is the General Ledger (GL)?**
  - Central record of all financial transactions of the company.
  - Organized by **accounts**, **companies**, **cost centers**, etc.
  - Source for **financial statements** and many Controllership reports.
- **What does a financial transaction look like?**
  - Has a **business event** (e.g. paying a supplier).
  - Is converted into one or more **journal lines** with debits and credits.
  - Includes **dimensions** like company, cost center, account, spend category.
- **How might this appear in a system like Workday?**
  - Business process: Supplier Invoice → Approval → Accounting rules → Posted to ledger.
  - Reports: Trial balance by account, supplier spend report by spend category.

If you can explain these in your own words, you’re already at a strong **junior+** to **mid‑level** conceptual level.

---

#### Exercise 4 – “Follow the Data” Story (with Answer)

**Question**  
Imagine an employee submits a travel expense in an external expense tool that integrates to Workday. Walk through **how that data flows** until a Controller sees it in a Power BI dashboard.

**Model answer** (one good way to say it):

1. Employee enters travel expense in the **expense tool** (source system).
2. The tool sends data to **Workday** via an **integration** (file/API, often through an EIB or middleware).
3. In Workday:
   - The expense becomes an **Expense Report / Supplier Invoice** type transaction.
   - **Business processes** ensure approvals (manager, finance).
   - **Accounting rules / Accounting Center** convert the approved expense into **journal lines**:
     - Debit: Travel Expense account (with spend category “Travel”).
     - Credit: Cash or Accounts Payable.
4. The journal lines are posted to the **GL** in Workday.
5. A scheduled integration loads **GL balances / journal lines** into the **data warehouse**.
6. Power BI is connected to the data warehouse tables and **refreshes its dataset**.
7. Controller opens the **Travel Spend dashboard** in Power BI and slices by:
   - Cost center, company, region, time period.

This answer shows:

- You understand **systems, data, and steps**, not just tool names.
- You can talk about **data lineage**, which is a senior‑style skill.

---

#### Exercise 5 – Data Integrity Case (with Answer)

**Question**  
Your BI report shows negative revenue for one cost center, but Workday shows positive revenue for that same cost center and period. How would you think about this?

**Model reasoning (what a senior would check):**

1. **Clarify the exact filters** used in both places:
   - Same company, ledger, period, currency?
2. **Check sign conventions**:
   - Some warehouses store revenue as negative numbers for consistency in calculations.
   - BI visuals might apply additional transformations.
3. **Compare counts**:
   - Number of revenue‑related journal lines in Workday vs warehouse.
4. **Verify ETL/refresh**:
   - When was the last successful data load to the warehouse?
   - Any failed or partial loads?
5. **Look for transformation logic**:
   - Are there any business rules that invert signs or exclude certain accounts?

The actual cause could be something simple (sign convention), but this structured approach shows you know **how to investigate** like an experienced person.

---

#### Exercise 6 – Role Explanation Practice (with Answer Template)

**Question**  
Explain what a “Workday Financial Systems Specialist” does to:

1. A non‑technical finance person.  
2. An IT integration developer.

**Model answer structure**

For **finance person**:

- “My job is to make sure Workday and our related systems support your financial processes smoothly. I help design and test changes to Workday, improve reports, and work with IT so that the data you see in Workday and dashboards is accurate and aligned with our policies.”

For **IT integration developer**:

- “I translate finance and Controllership requirements into clear system changes. I help specify what data needs to move between Workday and external systems, validate that mappings and accounting rules are correct, and coordinate user testing and sign‑off on your integration changes.”

If you can deliver this confidently, you sound already **mid‑level+**.

