# Data Integrity & ALCOA+

## Simple explanation
Data integrity = data stays **complete, consistent and accurate throughout its whole life**, and you can show who did what. Regulators issue many warning letters for failures here (deleted test results, shared logins, backdating).

## ALCOA+
| Letter | Meaning | Violation example |
|---|---|---|
| **A**ttributable | Who did it, when | shared login "admin" |
| **L**egible | Readable, permanent | overwritten pencil entries |
| **C**ontemporaneous | Recorded at time of action | filling logs at end of week |
| **O**riginal | First capture / certified copy | only keeping screenshot |
| **A**ccurate | Correct, error-free | unvalidated formula in Excel |
| + **C**omplete | Nothing deleted, incl. repeats | "testing into compliance" (rerun until pass, discard fails) |
| + **C**onsistent | Chronological, same format | timestamps out of order |
| + **E**nduring | Lasts retention period | thermal paper fading |
| + **A**vailable | Retrievable for audit | data on a dead server |

## Technical controls (what you'd build)
- Unique user IDs, role-based access, no shared accounts
- Immutable **audit trails** (who/what/when/old value/new value/reason)
- Time sync (NTP) and time zone handling
- Write-once storage / append-only tables / soft deletes only
- Hash checksums on files, backup + restore tests
- Locked configuration; spreadsheets validated + protected
- Data lineage (source → transformation → output)
- Reconciliation counts between pipeline stages

## SQL idea: audit trail table
```sql
CREATE TABLE audit_trail (
  audit_id BIGINT IDENTITY PRIMARY KEY,
  table_name VARCHAR(100), record_pk VARCHAR(100), column_name VARCHAR(100),
  old_value NVARCHAR(MAX), new_value NVARCHAR(MAX),
  changed_by VARCHAR(100) NOT NULL, changed_at_utc DATETIME2 NOT NULL DEFAULT SYSUTCDATETIME(),
  reason VARCHAR(500) NOT NULL
);
-- App role gets INSERT only; no UPDATE/DELETE on this table.
```

## Interview angle
"How would you design a pipeline that is GxP-compliant?" → traceability, immutability, access control, validation, change control, monitoring, documented SOPs.

## Resources
- MHRA GxP data integrity guidance (search title, gov.uk)
- FDA Data Integrity Q&A guidance (fda.gov)
- FDA Warning Letters database (read real failures): https://www.fda.gov/inspections-compliance-enforcement-and-criminal-investigations/compliance-actions-and-activities/warning-letters
- Link: [[21-CFR-Part-11]], [[Inspections-and-Audits]]
