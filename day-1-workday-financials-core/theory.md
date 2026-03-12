### Day 1 – Theory: Workday Core Worker & Org Model (Very Deep Dive)

Day 0 gave you the **big picture**. Day 1 zooms into the **people + structure side of Workday**, because:

- **Every approval**, many security rules, and a lot of reporting hinges on:
  - Who reports to whom.
  - Which org a worker sits in.
  - Where they are located.
  - What position and job they have.

If you master this mental model, you will immediately stand out in Workday Financials conversations.

---

## 1. Workday Core Objects Around People – Mental Map

Think of a worker in Workday as being surrounded by several key objects:

```text
             +------------------+
             |  Job Profile     |  (type of job: Accountant, Analyst)
             +------------------+
                        ^
                        |
                 +------+------+
                 |  Position   |  (specific seat)
                 +------+------+
                        ^
                        |
   +--------------------+--------------------+
   |                                         |
   v                                         v
+------+----------------+         +----------------------+
| Supervisory Org       |         | Location             |
| (who manages whom)    |         | (where worker sits)  |
+-----------------------+         +----------------------+
                        ^
                        |
                  +-----+-----+
                  | Worker    |
                  +-----------+
```

Key ideas:

- **Worker** sits in:
  - Exactly one **Position** (for most implementations).
  - One **Supervisory Org** (drives line manager and approvals).
  - One **Location** (city/site/country; impacts tax, compliance, reporting).
- **Position** is tied to a **Job Profile** and often to **default cost center / company / location**.
- These relationships are **critical** for:
  - Routing **approvals** (e.g. manager approval, org‑based approvals).
  - Determining which **cost centers / companies** costs are assigned to.
  - **Security and reporting** (who can see what).

---

## 2. Supervisory Orgs – The Backbone of Many Approvals

### 2.1 What is a Supervisory Org?

Plain explanation:

- A **Supervisory Organization** is a **grouping of workers** who report (directly or indirectly) to a manager.
- It’s about **who manages whom**, not about legal or financial structures (those are companies, cost centers, etc.).

Diagram (simplified):

```text
Company: ACME Corp

Supervisory Org: Finance - Corporate
  Manager: Director of Finance
  Workers:
    - Senior Accountant
    - Staff Accountant
    - AP Analyst
```

Why it matters:

- Many **approval chains** use:
  - “Manager of worker’s supervisory org” as a step.
  - “Manager’s manager” or “up the supervisory org hierarchy” for escalations.
- If orgs are misaligned:
  - Approvals go to the wrong people.
  - Data visibility and reporting become confusing.

### 2.2 Supervisory Orgs and Finance

Even though they are HR‑ish, they impact finance by:

- Driving **who approves financial‑impacting actions** (e.g. expenses, time, comp changes that hit payroll costs).
- Affecting **cost allocations** in some designs (if defaults are based on org).
- Influencing **segregation of duties** (SoD) and compliance (who can initiate vs approve).

Think like a senior:

- When you hear “approval issue”, ask:
  - “Is this due to supervisory org setup?”
  - “Has the worker moved but org wasn’t updated?”

---

## 3. Locations – Where the Work is Happening

### 3.1 What is a Location?

- Represents a **physical or logical place**:
  - Office, site, branch, remote region, etc.
- Workers are assigned to a location.

### 3.2 Why Locations Matter

- **Compliance & Tax**:
  - Different locations may have different payroll/tax rules.
- **Security & Reporting**:
  - Some orgs restrict access by location.
  - Reports often slice data by location.
- **Financial Analysis**:
  - Management might want cost by location.

As a Workday Specialist, when there’s a request like:

- “Show headcount and payroll cost by country/city.”

…you should immediately think:

- “We need correct **locations** on workers, and reporting that uses those fields.”

---

## 4. Positions vs Job Profiles – Seats vs Job Types

### 4.1 Job Profiles

- Describe the **kind of job**:
  - Title, responsibilities, competencies.
  - Example: “Senior Accountant”, “Financial Analyst”.
- Many workers can share the **same job profile**.

### 4.2 Positions

- Describe a **specific seat in the organization**:
  - There is usually a one‑to‑one link between **position and worker** (for filled positions).
  - Positions can be:
    - **Filled** (occupied by a worker).
    - **Unfilled** (open requisition or future plan).
  - Positions know:
    - Which **supervisory org** they’re in.
    - Default **cost center**, **company**, **location**, and sometimes **job profile**.

Think:

- Job Profile = “Senior Accountant” (role template).  
- Position = “Senior Accountant – Europe Controllership – Seat #1234”.

### 4.3 Financial Impact

- When a worker moves from one **position** to another:
  - Their **cost center, company, and maybe location** often change.
  - This impacts:
    - Payroll allocation.
    - Cost reports by department.
    - Budget vs actuals analyses.

---

## 5. Job Changes – Why They Are Critical for Finance

### 5.1 What is a Job Change in Workday?

- A **Job Change** is a Workday business process that modifies aspects of a worker’s job, such as:
  - Supervisory org (manager).
  - Position.
  - Location.
  - Job profile.
  - Compensation and sometimes cost center / company (depending on design).

High‑level flow:

```text
Initiate Job Change
    │
    ▼
Enter new details (position/org/loc/comp/etc.)
    │
    ▼
Approvals (e.g. current manager → new manager → HR → maybe Finance)
    │
    ▼
Completion (worker now sits in new org/position/loc)
```

### 5.2 Why Finance Cares

- Changes may:
  - Move costs between **cost centers / companies / locations**.
  - Impact who can approve **financial processes** for that worker.
  - Affect **segregation of duties** (e.g. person both initiates and approves certain transactions).

Typical senior thought process:

- When a business user asks:
  - “Why is this worker’s expense going to the wrong cost center?”
  - You check:
    - Their **position**, **cost center**, and recent **job changes**.
    - Whether the Job Change was fully processed and effective on the right date.

---

## 6. Delegations – Keeping Work Moving

### 6.1 What is a Delegation?

- A **delegation** lets one worker temporarily assign their **tasks and approvals** to another worker.
- Example:
  - Manager goes on vacation for two weeks.
  - Delegates approvals to another manager so **expenses, journals, purchase orders, etc.** don’t get stuck.

### 6.2 Why Delegations Matter to Controls and Finance

- Delegations help:
  - Maintain **business continuity**.
  - Avoid **backlogs** in approvals that delay financial processes.
- But they can also create risk if:
  - Delegations are mis‑configured or misused.
  - Approvals end up with someone who should not have that responsibility.

Senior mindset:

- Always think:
  - “Is this delegation **time‑bound**, **appropriate**, and **logged**?”
  - “If there’s an approval anomaly, check: is a delegation active?”

---

## 7. Business Processes (BP) – How Work Actually Flows

### 7.1 BP Components at a Glance

A Workday business process is essentially:

```text
Trigger/Event → Sequence of Steps → Completion
```

Steps can be:

- Approvals.
- Reviews.
- Notifications.
- Integrations.
- To‑dos for manual actions.

### 7.2 Example: Job Change BP (Conceptual)

```text
1. Initiate Job Change (HR Partner / Manager)
2. Manager Approval
3. HR Partner Review
4. (Optional) Comp Partner Review
5. (Optional) Security / IT Notification or Integration Step
6. Complete
```

For this JD, key focus areas:

- **Who approves what and why**.
- **What data changes at each step**.
- **What happens if a step is skipped or misrouted**.

---

## 8. End-to-End Impact Example – From Org Change to Financial Reports

Let’s walk a full example conceptually.

### 8.1 Scenario: Senior Accountant moves from “Corporate Finance” to “Revenue Operations”

- Before:
  - Supervisory Org: “Finance – Corporate”.
  - Cost Center: 1000 (Corporate Finance).
  - Location: New York.
- After:
  - Supervisory Org: “Finance – Revenue Ops”.
  - Cost Center: 2000 (Revenue Operations).
  - Location: stays New York.

**Theoretical impact:**

- Future **payroll costs** for this worker should hit Cost Center 2000 instead of 1000.
- **Approvals** for their timesheets/expenses might route to a different manager/org.
- Any **reports by cost center** will show their costs under a different area going forward.

**Practical impact and what you’d check as a Workday Specialist:**

- Was the **Job Change BP** completed with the correct **effective date**?
- Did the **position defaults** (cost center, org) update as expected?
- Are **recent payroll or expense entries** reflecting the new cost center?
- Is the new manager:
  - Able to see and approve their tasks?
  - Seeing them in the correct org in org charts/reports?

This is exactly the kind of cross‑functional thinking that marks someone as mid/senior.

---

## 9. Common Real-World Problems and How This Model Helps

Here are some frequent issues seniors encounter, and how you can reason about them:

### 9.1 Problem: Expenses Routed to Old Manager

- Symptom:
  - Worker’s job change completed, but expense approvals still go to previous manager.
- Likely root causes:
  - Expense report was **initiated before** the job change effective date.
  - Delegation or specific **BP configuration override** in place.
- How you’d think:
  - Check BP history for **Job Change** (effective date and completion).
  - Check **worker’s current org/position** vs at time of expense.
  - Check for **delegations or custom routing rules**.

### 9.2 Problem: Costs Hitting the Wrong Cost Center

- Symptom:
  - Payroll or expenses for a worker are still going to old cost center 1000.
- Possible causes:
  - Position still has old **default cost center**.
  - Job Change updated org but not cost center field.
  - Integration used **hard‑coded mapping** not updated.
- Senior mental checklist:
  - “Is this a **config issue** (position defaults), a **process issue** (wrong values entered), or an **integration issue**?”

---

## 10. Summary – What You Must Take Away from Day 1 Theory

By the end of this file, you should:

- Have a clear **mental map** of:
  - Worker ↔ Position ↔ Job Profile.
  - Worker ↔ Supervisory Org.
  - Worker ↔ Location.
- Understand how **job changes and delegations** drive:
  - Approvals.
  - Data visibility.
  - Financial impacts through cost center/company/location.
- Be ready to tackle **scenarios** in the Day 1 exercises and Q&A that simulate real org/worker issues.

Next, move to `practical-exercises.md` and `qa-and-scenarios.md` to make this theory feel real and automatic.

