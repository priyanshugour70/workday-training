### Day 5 – Theory: Workday Integrations, EIBs & Data Warehouse

#### 1. Workday Integration Landscape (High Level)

- Typical integration needs for Financial Systems:
  - **Bank integrations** (payments, bank statements, positive pay).
  - **Vendor systems** (AP automation, expense tools, procurement platforms).
  - **HR/Payroll** feeds.
  - **Data warehouse** loads for analytics.
- Integration patterns:
  - File‑based (CSV, XML).
  - Web services / APIs.
  - Scheduled vs real‑time.

#### 2. Workday EIBs (Enterprise Interface Builder)

- **Purpose**
  - Rapidly build **inbound or outbound** file‑based integrations without heavy custom development.
- Key concepts:
  - **Inbound EIB** – load data into Workday (e.g. journal entries, supplier loads).
  - **Outbound EIB** – extract Workday data for a downstream system.
  - **Templates and mappings** to align external files with Workday fields.

Even at a conceptual level, knowing **what EIBs can and cannot do** is valuable in this JD.

#### 3. Data Warehouse & Data Quality

- **Data warehouse**:
  - Central store combining **Workday** and **non‑Workday** data.
  - Structured for **reporting and analytics** (fact and dimension tables).
- Data integrity responsibilities in this JD:
  - **Detect** issues (missing, inconsistent, or unexpected values).
  - **Investigate** root cause (source system vs integration vs transformation).
  - **Escalate** to appropriate owners (Controllership, IT, vendor).
  - **Document** issues and remediation steps clearly.

