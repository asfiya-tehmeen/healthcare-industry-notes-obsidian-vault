# Computer System Validation (CSV) & CSA

## Simple explanation
Validation = documented proof that a system does what it is supposed to do, **consistently**, for its intended use. Like a driving test + paperwork.

## GAMP 5 software categories
1. Infrastructure (OS, DB) 3. Non-configured product 4. Configured product (most SaaS: Veeva, SAP) 5. Custom code (your Python pipelines, macros). Higher category → more testing.

## The V-model
```
URS (user requirements) ─────────────────────► PQ / UAT (performance)
   FS (functional spec) ─────────────────► OQ (operational testing)
      DS (design spec) ──────────────► IQ (installation)
                 Build / configure
```
- **Validation Plan (VP)** – scope, approach, roles.
- **Risk assessment** – decide test depth.
- **Traceability matrix (RTM)** – requirement ↔ test ↔ result.
- **Test scripts** with expected results, screenshots, signatures.
- **Deviation handling**.
- **Validation Summary Report (VSR)** → release.
- Then **change control**, **periodic review**, **retirement/archive**.

## CSA (Computer Software Assurance)
FDA's newer, risk-based approach: less paperwork for low-risk functions, more critical thinking, unscripted/exploratory testing allowed, vendor evidence leveraged. Draft/final guidance for production & quality-system software.

## Data pipeline validation example
| Requirement | Test |
|---|---|
| Row counts match source | reconcile source vs target |
| Derived age correct | known inputs → expected outputs |
| Only authorized users run | try with unauthorized role |
| Failed job alerts | force failure |
| Re-run is idempotent | run twice, compare |
Store tests as code in Git (pytest/dbt tests) + signed reports = modern validated-as-code.

## Roles
System owner, process owner, QA, validation lead, IT, vendor.

## Resources
- ISPE GAMP 5 guide: https://ispe.org
- FDA CSA guidance: search "Computer Software Assurance for Production and Quality System Software"
- Book: *GAMP 5 Guide* (ISPE) – see [[13-Resources/Books]]
- Related: [[GxP-Overview]], [[21-CFR-Part-11]]
