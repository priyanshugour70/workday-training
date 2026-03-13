### How Can We Build an EIB Integration (Step-by-Step)

This file is a **generic EIB playbook** you can reuse for any object (journals, suppliers, workers, etc.).

---

#### 1. Clarify the Business Need (Before Touching Workday)

- **Questions to ask:**
  - What data do we want to move? (e.g. journal entries, supplier data, worker updates)
  - Is it **one-time** or **recurring**?
  - Who owns the **source data** and who owns the **target** (Workday)?
  - What are the **controls** (approvals, reconciliation) around this load?
- **Deliverable**: short requirement note (1–2 pages) describing:
  - Purpose, frequency, source system, target object, volume, and success criteria.

---

#### 2. Identify the Right EIB / Template

- In Workday:
  - Find the delivered **EIB or loading task** for your object, e.g.:
    - Journals – “Load Journal Entry” (or similar).
    - Suppliers – supplier import EIB.
    - Workers – “Import Employee” / “EIB for Workers” (depends on tenant design).
- Download the **template** (Excel/CSV) from Workday.
- Review:
  - Column names (Workday fields).
  - Required vs optional columns.
  - Any notes on formats (dates, amounts, IDs).

---

#### 3. Design the Mapping From Source → Workday Template

- Create a **mapping sheet** (Excel or doc) with columns:
  - Source system field name.
  - Workday EIB template column.
  - Transformation rules (e.g. date format, concatenation, default values).
- Pay special attention to:
  - **Identifiers** (Company IDs, Ledger IDs, Account IDs, Worker IDs).
  - **Code sets** (e.g. country codes, currency codes).
  - **Required fields** (must never be blank).

This mapping document becomes your reference for both business and IT.

---

#### 4. Build and Validate a Sample File

- Take a **small sample** of data (5–20 rows).
- Populate the EIB template according to your mapping:
  - Ensure dates, numbers, IDs, and text match expected formats.
- Validate with business:
  - “Is this what you expect to see going into Workday?”

---

#### 5. Run a Test EIB in a Non-Production Tenant

- In Workday (sandbox/test):
  - Use the relevant EIB upload/load task.
  - Upload the sample file.
  - Run the EIB.
- After run:
  - Check **status** (success/failure).
  - Review any **error messages** (missing IDs, invalid formats, business rule violations).
  - Fix the file or mapping and re-run until you get a clean load.

---

#### 6. Verify Data in Workday

- Use reports or direct views to confirm:
  - Records created/updated as expected.
  - Key fields (amounts, dates, IDs, dimensions) are correct.
- For financial data:
  - Run **trial balance** or other related reports to confirm totals.
  - Make sure accounting rules behaved correctly (for journals, etc.).

---

#### 7. Plan for Recurring / Automated Loads (If Needed)

If integration is recurring:

- Decide:
  - Where the file will come from (source system export, manual Excel, etc.).
  - Where it will be placed (e.g. secure SFTP location).
  - How often it runs (daily, weekly, monthly).
- With IT/integration team:
  - Configure scheduled job/EIB integration to:
    - Pick up file.
    - Run the EIB.
    - Log success/failures and notify owners.

---

#### 8. Controls and Error Handling

- Define:
  - **Who reviews** EIB results after each run.
  - What to do if:
    - Entire file fails.
    - Some rows fail, some succeed.
  - How to **reverse or correct** bad data (e.g. reverse journals, correct supplier records).
- Document:
  - Common errors and how to fix them.
  - Checklists to run after each load (e.g. control totals, spot checks).

---

#### 9. Documentation and Training

- Produce:
  - A **step-by-step user guide** (with screenshots if allowed in your environment) for:
    - Preparing the file.
    - Uploading/running the EIB.
    - Checking results.
  - A **technical note** (if needed) for IT:
    - File locations, schedule, error notifications.
- Train:
  - End users who will prepare or approve data.
  - Support teams who will handle issues.

---

#### 10. Checklist: “Are We Ready to Go Live With This EIB Integration?”

- [ ] Business requirement documented and agreed.
- [ ] Correct EIB/template identified and tested in non-prod.
- [ ] Mapping document is complete and reviewed.
- [ ] Sample file loads successfully; data validated in Workday.
- [ ] Error handling and controls defined.
- [ ] If recurring: schedule, file location, and notifications configured.
- [ ] Documentation and training delivered.

This is the **standard pattern** you can reuse for almost any EIB-based integration initiative.

