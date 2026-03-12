### Day 0 – Core Concepts (Very Deep Dive)

The idea of Day 0 is: **you open this folder and, just by reading here, you go from 0 → strong conceptual understanding** of:

- What a **Workday Financial Systems Specialist** actually does every day.
- How **Workday Financials + Prism + Accounting Center + Adaptive Planning + Reporting** fit together.
- How this all connects to **finance, accounting, data, and analytics**.

Use it like a **mini‑book**. Read slowly, pause, draw the diagrams for yourself, and then go try the exercises.

---

#### 1. What is a Workday Financial Systems / Workday Specialist (Based on Real JDs)

At a high level, this role sits **in the middle of**:

- The **business** (Controllership, Finance, Accounting, FP&A, Operations).
- The **technology** (Workday Financials, data warehouse, integrations, vendors).

You are the **bridge** that makes sure:

- Systems correctly reflect **business rules and policies**.
- Data is **accurate, complete, and trusted**.
- Users can actually **do their jobs** (approve, post, report, analyze) without getting blocked by system issues.

Think of it like this:

```text
Business Problems / Processes
          │
          ▼
  Workday Specialist (you)
  ├── Understand finance + accounting
  ├── Understand Workday + data + tools
  └── Design + configure + support solutions
          │
          ▼
  Workday + Data Warehouse + BI
```

**Typical responsibilities (mapped to what you will learn in this repo):**

- **Discover improvements**
  - Talk to Controllers / Accountants about pain points: slow close, reconciliation issues, manual Excel steps.
  - Identify **where Workday or reporting can automate or improve** the process.
- **Design business requirements**
  - Write down: current process, problem, desired outcome, data needed, affected teams.
  - Convert into **clear, structured requirements** IT/Finance Systems can build from.
- **Configure/Test/Implement**
  - Example: new **spend category**, updated **approval chain**, or new **report**.
  - You help design, sometimes configure, and always **test with business users**.
- **Data & issue resolution**
  - Notice **data mismatches** between Workday vs Power BI vs data warehouse.
  - Investigate, identify **root cause**, and work with the right team to fix.
- **Documentation & communication**
  - Write **how‑to guides**, change summaries, and explain complex issues in simple language.

---

#### 2. The Workday Financials Ecosystem – Big Picture Map

When people say “Workday” in this context, they usually mean a **set of components working together**:

```text
          +-----------------------------+
          |  Workday Financials Core    |
          |  (GL, AP, AR, Assets, etc.) |
          +--------------+--------------+
                         |
                         v
              +----------+-----------+
              | Workday Accounting   |
              | Center               |
              | (operational → GL)   |
              +----------+-----------+
                         |
                         v
             +-----------+-----------+
             |   Financial Data in   |
             |   Workday (GL, subledg)|
             +-----------+-----------+
                         |
        +----------------+---------------------+
        |                                      |
        v                                      v
+---------------+                     +----------------+
| Workday Prism |                     | Data Warehouse |
| (analytics)   |                     | (enterprise)   |
+-------+-------+                     +--------+-------+
        |                                       |
        v                                       v
  Workday Reports & Dashboards            Power BI / Other BI
```

- **Workday Financials Core**
  - Where **transactions** live:
    - Journals, supplier invoices, customer invoices, expenses, assets, etc.
  - Where structures live:
    - Companies, cost centers, spend categories, ledger accounts, projects.

- **Workday Accounting Center**
  - Takes **operational data** (HR events, expenses, etc.) and converts it into **accounting entries** using rules.
  - Ensures consistent, rules‑based **debits and credits**.

- **Workday Prism Analytics**
  - A **data hub** that combines **Workday data + external data** (bank files, legacy systems, external systems).
  - Used to build more advanced analytics without leaving the Workday ecosystem.

- **Adaptive Planning**
  - Used by FP&A, finance, and sometimes Controllership for **budgets, forecasts, and scenarios**.
  - Pulls **actuals from Workday**, allows planners to create plans, and can push planned data back.

- **Reporting**
  - Workday’s own reporting layer: standard & custom reports, dashboards, composites.
  - Often the **first place finance goes** for operational and financial data.

You don’t need to be a deep config expert on Day 0, but you must be able to **verbally walk through this picture**.

---

#### 3. Why Businesses Need a Workday Financial Systems Specialist

Use this table as a “why this role exists” graph in text form:

| **Business Need** | **Why it Matters** | **Where You Touch It (Systems)** | **Concrete Example** |
|-------------------|--------------------|-----------------------------------|-----------------------|
| Fast, accurate month‑end close | Late or wrong financials hurt decision‑making and compliance | Workday Financials, Accounting Center, reports, data warehouse | Ensure journals from subsystems post correctly and reports tie out |
| Trusted financial reports | Executives must trust numbers to make decisions | Workday reporting, Prism, Power BI | Investigate mismatch between Workday trial balance and BI dashboard |
| Strong internal controls | Avoid fraud, errors, audit findings | Workday business processes, approvals, delegations | Design approval flows so high‑risk journals always have dual approval |
| Automation instead of manual Excel | Manual steps are slow and error‑prone | Workday config, integrations, EIBs | Replace manual journal uploads with validated EIB process |
| Clear policies & documentation | New staff and auditors need clarity | Documentation, training, change management | Write step‑by‑step guides for new expense policy in Workday |

When you answer **“Why does this role matter?”** in an interview, you can pick lines directly from this table.

---

#### 4. Finance & Accounting Fundamentals (With Workday Lens)

You don’t need to be a CPA, but you **must** understand some basics very well:

##### 4.1 Accounting Equation and Elements

- Accounting equation:  
  \[
  \text{Assets} = \text{Liabilities} + \text{Equity}
  \]

- Elements:
  - **Assets**: what the company owns (cash, receivables, equipment).
  - **Liabilities**: what the company owes (loans, payables).
  - **Equity**: owner’s stake (capital, retained earnings).
  - **Revenue**: money earned from operations.
  - **Expenses**: costs incurred to earn revenue.

In Workday, these show up as **ledger accounts** with types (asset, liability, etc.).

##### 4.2 Debits and Credits (Conceptual)

- Every transaction has **two sides**:
  - Example: Pay supplier:
    - Debit: Accounts Payable (liability goes down).
    - Credit: Cash (asset goes down).
- In Workday:
  - You don’t usually type “debit/credit” manually.
  - **Accounting rules (and Accounting Center)** generate them from events.

You need to understand this to:

- Read **journal lines** and **trial balance**.
- See if mapped accounts and signs “make sense”.

##### 4.3 Financial Statements – How Workday Supports Them

High‑level view:

```text
Operational events (HR, procurement, billing, etc.)
       │
       ▼
  Accounting rules / Accounting Center
       │
       ▼
  Journal Entries in Workday Financials
       │
       ▼
  General Ledger (GL balances)
       │
       ▼
  Financial Statements (via Workday reports / BI)
```

As a Workday Specialist, you must be able to say:

- “This business process or transaction **ultimately affects** these GL accounts and these reports.”

##### 4.4 How Workday Represents Finance Structures

| **Traditional Concept** | **In Workday** | **What You Should Know on Day 0** |
|-------------------------|----------------|-----------------------------------|
| Legal entity | Company / Company hierarchy | Companies often map to legal entities; important for reporting & tax |
| General Ledger | Ledger(s) & ledger periods | Basic idea of ledgers and periods; month‑end close happens here |
| Chart of Accounts | Ledger accounts + other dimensions | How accounts + cost centers + spend categories combine |
| Cost centers / departments | Cost center dimension | Used for managerial reporting, budgeting, analysis |
| Expense categories | Spend categories | Front‑end category that maps to one or more GL accounts |

Later days (Day 2 etc.) go deeper, but you should already understand **the mapping idea** on Day 0.

---

#### 5. The Tools Side – SQL, Power BI, Office, and Why They Matter

##### 5.1 SQL (Structured Query Language)

**Why it appears in the JD:**

- When someone says “The numbers in this BI report look wrong,” you need to:
  - Query **raw tables** (in a data warehouse or staging area).
  - Check counts, sums, and filters.

**Mental model:**

```text
Table: fact_journal
Columns: posting_date, company, cost_center, account, amount, currency
```

Basic things you must be comfortable with (conceptually on Day 0, practice later):

- `SELECT` – choose columns.
- `WHERE` – filter rows (e.g. one company, date range).
- `GROUP BY` – summarize data (e.g. total spend by cost center).

##### 5.2 Power BI

**Why business cares:**

- Controllers, finance leaders, and operations teams want:
  - Trend views (month over month).
  - Slicers for company, cost center, region.
  - Visuals they can quickly interpret.

**Your role:**

- Help ensure the **dataset is correct**.
- Sometimes help design **which fields** and **filters** are needed.
- Understand enough to **debug obvious data issues** (e.g. wrong date, missing filters).

##### 5.3 Office (Excel, PowerPoint, Outlook)

- **Excel**: still heavily used for:
  - Ad‑hoc analysis.
  - Validating Workday vs BI numbers.
  - Data prep for uploads (e.g. EIB files).
- **PowerPoint**:
  - Explaining **issues, designs, or project status** to leadership.
- **Outlook / Email**:
  - Communicating issues and solutions in a clear, structured way.

---

#### 6. Typical “Day in the Life” Scenarios (With Q&A)

Use these as scenario‑based preparation. Imagine how you would respond.

##### Scenario A – Data Mismatch Between Workday and Power BI

- **Situation**: Controller says, “Workday trial balance shows \$10M expense, but our Power BI dashboard shows \$9.5M.”
- **Likely causes** (think in systems):
  - BI is using a **different date range** or **different ledger**.
  - BI dataset is **not refreshed** but Workday is up to date.
  - A **subset of journals** (e.g. one company, one ledger) is excluded in BI filters.
  - Data warehouse load/ETL issue.
- **What you (Workday Specialist) would do at a high level**:
  - Confirm **exact filters** used in Workday report vs BI.
  - Check **last refresh time** of BI dataset.
  - Use **SQL** (or help from data team) to query raw balances.
  - Identify specific **accounts or cost centers** that differ.

**Interview‑style question:**  
“How would you approach a mismatch between Workday and a BI report?”  
**Answer structure (short):**

- I would first confirm the **scope and filters** in both tools, then check **data refresh and ETL** timings, and finally validate numbers at a granular level (by account, cost center, or journal) using **reports and, where available, SQL**. I’d document findings and work with Controllership and IT to fix root causes.

##### Scenario B – New Spend Category Request

- **Situation**: Procurement wants a new spend category “SaaS Subscriptions” to separate software spend.
- **Questions you should ask**:
  - What **GL account(s)** should this map to?
  - Are there any **approval differences** compared to existing categories?
  - Which **companies / cost centers / regions** will use it?
  - Are there any **reporting requirements** (new dashboard, new line item in P&L)?
- **Your involvement**:
  - Capture clear **requirements**.
  - Coordinate with whoever configures Workday to create the **spend category + mapping**.
  - Help design or adjust **reports** to highlight this new category.

##### Scenario C – Audit / Control Concern

- **Situation**: Internal audit finds journals above a certain amount are being posted with only one approval.
- **Your high‑level actions**:
  - Review **current business process configuration** for journal approvals.
  - Propose updated **approval rules** based on amount thresholds and companies.
  - Help **test** new configuration and document the change.

These scenarios will come back in later days with deeper detail. On Day 0, you just need to understand **who is involved** and **which systems** are touched.

---

#### 7. Mental Models to Carry into the Rest of the Plan

1. **Everything is data flowing through systems**
   - From **source events** (HR, invoices, payments) → **rules and mappings** → **GL entries** → **reports / BI**.
2. **Your value is in connecting dots**
   - Between **business language** (“our travel cost is too high”) and **system language** (spend categories, accounts, cost centers, filters).
3. **Documentation and communication are as important as config**
   - A good Workday Specialist doesn’t just fix issues; they **explain and prevent** them.

Read this file once just to absorb. Then come back later and:

- Turn the text diagrams into **your own drawings**.
- Rewrite definitions in **your own words** (this helps memory a lot).

### Day 0 – Core Concepts to Understand

#### 1. Workday Specialist Role (from JD)

- **Core responsibility**: Support and enhance the **Financial Systems Platform** (mainly Workday Financials).
- **Key partners**: Controllership, Finance, Accounting, IT, and 3rd‑party vendors.
- **Core activities**:
  - Discover potential **process and system improvements**.
  - Translate business needs into **clear business requirements**.
  - **Configure/Test/Implement** solutions in Workday and integrations.
  - **Support end users** and resolve **data issues**.

#### 2. Workday Financials Ecosystem (High Level)

- **Workday Financials Core** – General Ledger, customers, suppliers, spend categories, cost centers, etc.
- **Workday Prism** – Analytics and data hub to bring Workday + non‑Workday data together.
- **Workday Accounting Center** – Turns operational events into accounting entries.
- **Adaptive Planning** – Planning, budgeting, and forecasting.
- **Reporting** – Workday reports and dashboards using internal data sources.

You do **not** need deep configuration knowledge on Day 0—only a **high-level understanding** of what each component is for.

#### 3. Finance & Accounting Fundamentals to Refresh

- **Basic accounting**:
  - Assets, Liabilities, Equity, Revenue, Expenses.
  - Debits vs Credits (at least conceptually).
  - Financial statements (Balance Sheet, Income Statement, Cash Flow).
- How Workday typically maps these into:
  - **Companies / Legal entities**
  - **Ledgers**
  - **Accounts / Spend Categories**
  - **Cost Centers / Cost objects**

#### 4. Tools in the JD

- **SQL**
  - Query tabular data.
  - Filter (`WHERE`), aggregate (`GROUP BY`), basic joins.
- **Power BI**
  - Connect to data source.
  - Create simple visuals and dashboards.
- **MS Office**
  - Excel fundamentals (pivot tables, vlookups or XLOOKUP, basic formulas).
  - PowerPoint basics for communicating analysis.

