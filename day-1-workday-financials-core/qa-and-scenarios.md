### Day 1 – Q&A and Scenario Bank (Orgs, Job Changes, Delegations)

Use this file to go **beyond basic understanding** into how seniors talk and think.

---

#### Q1. “Why does the supervisory org structure matter so much for finance if it’s ‘just HR’?”

**Strong answer:**

- Supervisory orgs determine:
  - Who **manages** which workers.
  - Who **approves** many HR and financial‑impacting processes (expenses, time, some journals, etc.).
- If supervisory orgs are wrong:
  - Approvals route to the wrong people or fail to route at all.
  - It becomes harder to understand **who owns which costs** or processes.
- Even though legal/financial reporting use companies and cost centers, the **day‑to‑day flow of work** (and controls) heavily depends on the supervisory structure.

---

#### Q2. “What can go wrong if a Job Change is done with the wrong effective date?”

**Conceptual risks:**

- Payroll or costs:
  - Labor costs may be charged to the **wrong cost center** for part of a period.
- Approvals:
  - Approvals may go to the **old manager** longer than intended, or start going to the **new manager too early**.
- Reporting:
  - Headcount by org or location may look wrong for certain dates.

**How a senior would investigate:**

- Check:
  - **Effective date** of Job Change vs date of problematic transactions (payroll, expenses, etc.).
  - BP history to confirm when the change actually completed.
  - Downstream processes (e.g. payroll run date) relative to that effective date.

---

#### Q3. “How do delegations interact with segregation of duties (SoD) concerns?”

**Good senior‑style explanation:**

- Segregation of duties means:
  - No single person should be able to both **initiate and approve** high‑risk transactions.
- Delegations can:
  - Help maintain continuity (someone is always able to approve).
  - But also accidentally:
    - Give temporary approvers too much power.
    - Create SoD violations if delegate and initiator are too close in the control chain.
- Mitigation:
  - Carefully choose **who** receives delegations (similar or higher level, appropriate domain).
  - Ensure delegations are **time‑bound** and **reviewed**.
  - Include delegated approvals in **audit reviews**.

---

#### Scenario A – “New Manager, Same Cost Center?” 

**Problem**  
Worker moves to a new supervisor but should still be financially in the same cost center. HR wants to change the supervisor only.

**How to think:**

- Identify:
  - Is this purely an **org/reporting chain change**, or does it impact **cost center/company**?
- If it is **only** reporting/manager change:
  - The Job Change should update the **supervisory org/manager** but keep cost center and financials the same.
- Risks:
  - If the new manager is in a different part of the org where default cost center differs, misconfiguration may **unintentionally move costs**.

**Answer structure:**

- Clarify with HR/Finance:
  - “Is cost reporting supposed to stay with the old area or move with the new manager?”
- Then:
  - Configure / perform Job Change accordingly.
  - Verify position and cost center fields **before and after**.

---

#### Scenario B – “Approvals Going to the Wrong Manager After Org Restructure”

**Problem**  
After creating new supervisory orgs and moving workers, expense approvals are still going to the old manager.

**Senior approach:**

- Hypotheses:
  - Expenses were initiated **before** Job Change effective date.
  - An **org‑based BP routing condition** is still pointing at the old org.
  - There is a **delegation** still pointing to old manager.
- Steps:
  1. Check an example expense’s **Business Process history**:
     - See which step and which person is assigned.
  2. Check worker’s **current supervisory org and manager**.
  3. Review BP config (or ask HRIS/config team) to confirm which fields are used for routing.
  4. Check for any **active delegations** for the new/old managers.

This shows you don’t just guess—you have a **structured diagnostic path**.

---

#### Scenario C – “Mass Move of Workers Between Orgs”

**Problem**  
Company is moving 200 workers from Org A to Org B due to reorganization. How would you think about executing this safely?

**High-level steps:**

1. **Plan with HR/Finance**:
   - Confirm which positions/workers move.
   - Clarify impacts on cost centers, companies, locations.
2. **Choose the mechanism**:
   - Individual Job Changes vs mass position/worker update tools (depending on tools available).
3. **Timing and effective dates**:
   - Align with payroll cycles and reporting periods.
4. **Testing**:
   - In a test environment:
     - Move a subset and check reports and approvals.
5. **Communication**:
   - Inform managers and impacted workers.
6. **Post‑move validation**:
   - Run reports:
     - Headcount by org.
     - Cost by org (future periods).
   - Check approval routing for key processes.

Even if you don’t push the buttons yourself, this thinking shows project‑level maturity.

---

Use this file like an **interview and thinking gym**: pick one Q or scenario per day, answer out loud, then refine using these model responses.

