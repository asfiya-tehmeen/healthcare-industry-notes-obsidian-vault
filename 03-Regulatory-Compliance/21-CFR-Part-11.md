# 21 CFR Part 11 (and EU Annex 11)

## Simple explanation
Part 11 says when FDA accepts **electronic records** and **electronic signatures** as equal to paper and handwritten ones. Annex 11 is the EU equivalent for computerised systems.

Text: https://www.ecfr.gov/current/title-21/chapter-I/subchapter-A/part-11

## Main requirements (Subpart B – electronic records)
- **Validation** of systems (accurate, reliable, consistent).
- Ability to generate accurate **copies** for inspection.
- **Record protection** & retrieval through retention period.
- **Access limited** to authorized individuals.
- Secure, computer-generated, time-stamped **audit trails**, not obscuring previous values.
- **Operational checks** (enforce step sequence), **authority checks**, **device checks**.
- Training of personnel; written policies on accountability for e-signatures.
- Controls on documentation (revision & change control).

## Subpart C – electronic signatures
- Unique to one person, never reused.
- Signature manifests show printed name, date/time, **meaning** (review, approval, authorship).
- Linked to its record (can't be copied/transplanted).
- Two components (ID + password) for non-biometric; Part 11 also covers open vs closed systems.

## Practical checklist for a system
- [ ] Individual accounts, password/MFA policy, lockout
- [ ] Role-based access matrix
- [ ] Audit trail on create/modify/delete of GxP data; cannot be disabled by users
- [ ] E-signature with meaning and re-authentication
- [ ] Validation package (see [[Computer-System-Validation]])
- [ ] Backup/restore and archival tested
- [ ] Periodic review of audit trails and access

## Annex 11 extras
Supplier assessment, data migration validation, business continuity, incident management, periodic evaluation, printouts of data for batch release.

## Common pitfalls
Excel for GxP calcs without controls; admin accounts with no audit; Jupyter notebooks changing regulated data; cloud SaaS without vendor audit.

## Resources
- FDA Part 11 Scope & Application guidance (search fda.gov)
- EU GMP Annex 11 (EudraLex Vol. 4, ec.europa.eu/health)
- Next: [[Data-Integrity-ALCOA]]
