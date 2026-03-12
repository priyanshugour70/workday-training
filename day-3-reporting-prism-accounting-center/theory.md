### Day 3 – Theory: Reporting, Prism & Accounting Center

#### 1. Workday Reporting Basics

- **Standard reports**
  - Delivered by Workday.
  - Often used as starting point to understand **available fields and data sources**.
- **Custom reports** (conceptual level for this plan)
  - Built on top of **data sources** (e.g. Workers, Journal Lines, Supplier Invoices).
  - Consist of:
    - Selected **fields** (columns).
    - **Filters** (WHERE conditions).
    - **Prompts** (parameters at runtime).
  - Can be secured and shared with appropriate audiences.

Reporting is central to this JD because Controllership relies on **accurate and timely information**.

#### 2. Workday Prism Analytics (Conceptual)

- **Purpose**
  - Bring together **Workday data** and **external data** (e.g. bank files, legacy systems) in one analytical environment.
  - Enable more complex analysis, blending, and transformations.
- For a Workday Specialist:
  - Understand where Prism fits in the **data architecture**.
  - Know that data must be **loaded, modeled, validated** before being exposed to users.

#### 3. Workday Accounting Center (Conceptual)

- **Goal**
  - Convert high‑volume operational events (HR, expenses, etc.) into **consistent accounting entries** using rules.
- Key ideas:
  - **Source data** (e.g. HR events).
  - **Transformation rules** to derive accounts, cost centers, other dimensions.
  - **Posting** to the General Ledger.

#### 4. Data Integrity & Reporting

- For Controllership to trust reports, you must ensure:
  - **Source data quality** (correct values coming from upstream systems).
  - **Correct mappings** (e.g. in Accounting Center, accounting rules, Prism transformations).
  - **Clear documentation** of data sources, filters, and transformations.

