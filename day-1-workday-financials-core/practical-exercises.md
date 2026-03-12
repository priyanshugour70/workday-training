### Day 1 – Practical Exercises (With Theory + Practical Answers)

> If you don’t have a tenant, do the **mental/practical simulation**.  
> If you do have a sandbox, try to validate what you read here.

For each exercise:

- First, answer on your own.
- Then, compare to the **theoretical** and **practical** model answers.

---

#### Exercise 1 – Map a Worker’s “Surroundings”

**Question (theoretical)**  
Pick a sample role (e.g. “AP Analyst”) and describe all the Workday objects around that worker that you care about as a Financial Systems Specialist.

**Model answer (theoretical view):**

- For an **AP Analyst**, I care about:
  - **Supervisory Org** – who they report to; this drives manager approvals.
  - **Position** – specific seat; contains default cost center/company/location.
  - **Job Profile** – role type; may impact eligibility rules and security.
  - **Location** – physical/virtual site; affects tax rules and reporting views.
  - **Cost center / Company** – financial dimensions tied to their labor cost.
  - **Security roles** – what financial tasks they can perform (view/post invoices, etc.).

**Model answer (practical/system view):**

- In Workday I would:
  - Search for the worker, open **View Position** / **View Job**:
    - Confirm **Position** details (org, cost center, company).
  - Use **Related Actions → Organization** to see their **Supervisory Org** and manager.
  - Check their **Location** (e.g. city/country) via worker’s profile.
  - Optionally, view **Security Group** membership (if I have access) to see their permissions.

---

#### Exercise 2 – Simple Navigational Drill (Conceptual)

**Question (theoretical)**  
Describe how an experienced Workday user quickly navigates to:

1. A worker’s supervisory org.  
2. The org’s manager.  
3. A list of workers in that org.

**Model answer (theoretical view):**

- They think in terms of:
  - Using **Search** to jump directly to the worker.
  - Using **Related Actions** to hop from worker → position → org.
  - Using standard org/worker reports to list members of that org.

**Model answer (practical/system view, typical path):**

- 1) In the global search, type the worker’s name and open their profile.
- 2) On the worker, open **Related Actions → Organization → Supervisory** (or equivalent link) to view their **Supervisory Org**.
- 3) On the org screen:
  - See the **Manager** field at the top.
  - Use a report or related action like “View Members” or “Org Chart” to see all workers in that org.

Even if labels differ slightly per tenant, this is how seniors think: **worker → org → manager → members**.

---

#### Exercise 3 – Job Change Scenario (Concept + Steps)

**Scenario**  
An “AP Analyst” in the “Finance – Corporate” org is moving to “Finance – Shared Services” with a new manager and cost center.  
You are asked: “What should we be careful about in Workday so finance and approvals don’t break?”

**Model answer (theoretical view):**

- Key concerns:
  - **Effective date** of the Job Change – must align with payroll/costing expectations.
  - **Position and Supervisory Org** – ensuring they move to the correct new org/manager.
  - **Cost center / company / location** – updated so future labor and related expenses hit the right dimensions.
  - **Business process approvals** – verifying the Job Change BP routes through appropriate HR/manager approvers.
  - **In-flight items** – existing tasks/approvals may still route to old manager if initiated before change.

**Model answer (practical/system view):**

- In Workday I would:
  - During Job Change:
    - Choose the correct **new position** or create one in the “Finance – Shared Services” org.
    - Confirm the **manager** and **org** on the new position.
    - Verify **cost center/company** fields on the position or worker.
    - Double‑check the **effective date**.
  - After Job Change completes:
    - Run or check a **report** showing the worker’s org, position, cost center, and manager.
    - Optionally test with a small **expense or time entry** (in a test environment) to ensure approvals go to the new manager.

---

#### Exercise 4 – Delegation Scenario (Continuity + Risk)

**Scenario**  
The Director of Finance is going on a 3‑week vacation during month‑end close. They approve high‑value journals and supplier invoices. How should delegations be set up so work continues but controls remain strong?

**Model answer (theoretical view):**

- Goals:
  - Avoid a backlog of critical approvals.
  - Maintain **appropriate approval authority** (no delegating to juniors who shouldn’t approve big amounts).
  - Ensure delegations are **time‑bound** and **transparent**.
- Key decisions:
  - Who receives delegated tasks? (typically another senior manager or above).
  - For which **BPs** or tasks? (journals, supplier invoices, expenses, etc.).
  - What **time range** is covered?

**Model answer (practical/system view):**

- In Workday, I would:
  - Set up a **delegation rule** for the Director:
    - Start date = day they leave.
    - End date = day before they return.
    - Delegate to a **peer leader** or someone with similar authority.
    - Ensure the delegation covers **approval steps** in the relevant BPs (journals, supplier invoices, etc.).
  - Communicate:
    - Let Controllership, AP, and relevant teams know who will be approving temporarily.
  - After they return:
    - Confirm delegations have **ended**.
    - Optionally review critical approvals that happened during the delegation period.

---

#### Exercise 5 – BP History Investigation

**Scenario**  
A business user says: “My job change request has been stuck for days. I don’t know who needs to act next.”  
You are asked to help.

**Model answer (theoretical view):**

- Approach:
  - Always look at **BP history** to see:
    - Which steps are completed.
    - Which step is in progress.
    - Who currently has the task.
  - Think about:
    - Is the task with a person who is absent?
    - Is there a missing configuration (e.g. no routing condition met)?

**Model answer (practical/system view):**

- In Workday I would:
  - Open the **Job Change event**.
  - View **Business Process Details / Process History**.
  - Identify:
    - The current step (e.g. “HR Partner Review”).
    - The **assignee(s)** for that step.
  - Actions:
    - If the assignee is available: notify them and/or resend the task.
    - If they are on leave: check for **delegations**, or work with HR/IT to **reassign** the step to the correct person.
    - If routing is broken: flag to the configuration/HRIS team to adjust BP setup.

---

#### Exercise 6 – Org Structure Change and Finance

**Scenario**  
The company is restructuring: the “Finance – Corporate” supervisory org will split into “Finance – Corporate HQ” and “Finance – Regional Shared Services”. Controllers ask: “What should we be careful about in Workday so our reports and approvals still make sense?”

**Model answer (theoretical view):**

- Consider:
  - **Who will manage each new org** (org managers and their span of control).
  - **Which workers** move to which new orgs.
  - How **positions** will be reassigned or recreated.
  - **Cost center alignment** with new orgs.
  - Impact on:
    - Approval routing.
    - Org‑based security.
    - Reports grouped by org.

**Model answer (practical/system view):**

- In Workday, as a Specialist I would:
  - Plan the creation of the new **Supervisory Orgs**:
    - Set managers.
    - Assign appropriate locations or default values.
  - Plan a bulk or phased movement of **positions/workers** to the new orgs (through position or job change processes).
  - Coordinate with Finance to:
    - Align **cost centers/companies** where necessary.
    - Update key **reports** and **filters** that used the old org.
  - Work with HR/IT to:
    - Review security roles tied to the old org.
    - Ensure **approvals** for key processes still follow desired lines (e.g. high‑value invoices go to the right leaders).

---

Use these exercises as **mental reps**: read the scenario, close your eyes, think through it, then check these answers and refine your own explanations. This is how you build near‑senior thinking without yet having 7–8 years in the job.

