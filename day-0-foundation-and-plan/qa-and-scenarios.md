### Day 0 – Q&A and Scenario Bank

This file is to push your understanding **to a near‑senior level** just by reading and thinking.  
Use it for:

- Interview prep.
- Deep thinking.
- Seeing how an experienced person structures answers.

---

#### Q1. “What are the biggest risks if Workday Financials is misconfigured?”

**Good senior‑style answer:**

- Misconfiguration can directly impact:
  - **Financial accuracy** – wrong accounts, missing entries, double postings.
  - **Controls and compliance** – missing approvals, incorrect segregation of duties.
  - **Operational efficiency** – users blocked or forced into manual workarounds.
- Concrete examples:
  - An incorrect mapping in **Accounting Center** routes high‑value expenses to the wrong GL account, causing mis‑stated P&L.
  - A misconfigured **approval chain** allows large journals to post with single approval, creating an audit finding.
  - A broken **integration** drops some transactions, so BI and Workday don’t match and close is delayed.
- As a Workday Specialist, my focus is to:
  - Catch these issues early via **testing and validation**.
  - Implement **controls and monitoring**.
  - Maintain clear **documentation** so changes are understood and reviewed.

---

#### Q2. “How do Workday Prism and the data warehouse coexist? Aren’t they the same thing?”

**Strong conceptual answer:**

- They both deal with **analytics**, but they serve **different scopes and audiences**:
  - **Workday Prism** focuses on extending analytics **within the Workday ecosystem**:
    - Blends Workday data with selected external data.
    - Great for work that is close to HR/Finance operations.
  - An **enterprise data warehouse**:
    - Centralizes data from **many systems** (Workday + CRM + legacy + others).
    - Powers wide BI tools like **Power BI**, enterprise dashboards, data science.
- In practice, a company might:
  - Use **Prism** for operational analytics close to Workday.
  - Feed key curated data from Workday/Prism into the **data warehouse** for broader analytics.
- As a Workday Specialist:
  - I care about making sure **data definitions and mappings** are consistent between Prism and the warehouse.
  - I help explain to business which tool is right for which type of analysis.

---

#### Q3. “Explain Accounting Center to a non‑technical Controller.”

**Simple but powerful explanation:**

- “Accounting Center is like a smart engine that turns our operational events into consistent accounting entries.”
- Instead of:
  - Having many different teams manually decide which accounts to use for each event.
- We:
  - Define **rules** in Accounting Center: if event is X with attributes A/B/C, then use **these accounts, cost centers, and other dimensions**.
- Benefits:
  - Consistent accounting across the company.
  - Easier to adjust rules when policies change.
  - Better data quality for reporting and audits.

---

#### Q4. “How would you handle a situation where a Controllership stakeholder is unhappy with a new Workday change?”

**Experienced mindset answer:**

- First, **listen and clarify**:
  - Understand exactly what is not working from their perspective: usability, missing data, timing, approvals, etc.
- Then, **analyze impact and root cause**:
  - Is the issue about **design** (requirements misunderstood), **configuration**, or **training/communication**?
- Next, **co‑create options**:
  - Present alternatives with pros/cons, such as:
    - Adjusting configuration (e.g. adding another field or step).
    - Creating a report or dashboard to surface missing information.
    - Updating documentation or delivering focused training.
- Throughout, **communicate clearly**:
  - Set expectations on what can be changed quickly and what needs more time.
  - Keep IT / vendors in the loop if they are involved.
- This answer shows:
  - Emotional intelligence.
  - Ownership.
  - Ability to balance technical constraints with business needs.

---

#### Q5. “What does ‘data integrity’ mean in this context, in practical terms?”

**Beyond buzzword answer:**

- It means:
  - **Completeness** – all relevant transactions are captured (no missing rows).
  - **Accuracy** – values, dates, accounts, and dimensions are correct.
  - **Consistency** – the same event looks the same across Workday, warehouse, and BI.
  - **Timeliness** – data is refreshed in line with business expectations (e.g. daily close activities).
- Practically, I think in terms of:
  - **Controls** – approvals, validation rules, reconciliation checks.
  - **Monitoring** – alerts for failed integrations or unusual patterns.
  - **Processes** – clear ownership of each data flow step.
- For this role, “a passion for data integrity” means:
  - I proactively look for anomalies.
  - I don’t accept “it’s probably fine” without evidence.

---

#### Q6. Scenario – New Bank Integration

**Problem**  
Company is implementing a new bank. Workday must send payment files and receive bank statements. You are the Workday Specialist on the project.

**How a senior would structure this:**

1. **Understand scope**
   - Payment types (ACH, wires, checks).
   - Countries/currencies, volumes, and timing.
2. **Identify integrations**
   - Outbound payment files: Workday → Bank.
   - Inbound bank statements: Bank → Workday and/or warehouse.
3. **Design with teams**
   - With **Treasury/Finance**:
     - File formats, approval thresholds, cut‑off times.
   - With **IT/integration team**:
     - Transport method (SFTP/API), security, error handling.
4. **Controls and testing**
   - Dual approvals for high‑value payments.
   - Test scenarios:
     - Successful payment.
     - Rejected payment.
     - Partial file or connectivity issues.
5. **Data + reconciliation**
   - Ensure Workday payment statuses align with bank statuses.
   - Plan how bank statements will reconcile with Workday cash/GL.

You don’t have to know every configuration screen, but if you can outline this kind of structure, you already sound very senior conceptually.

---

Use this file regularly:

- Read one question.
- Pause, answer out loud.
- Then compare to the model answer and improve your structure and vocabulary.

