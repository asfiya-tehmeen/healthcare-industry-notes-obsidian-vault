# Compliance Case Exercises (think like an auditor)

For each: write a 1-page answer. Then compare with an AI or mentor.

1. **Shared login.** A lab technician uses colleague's login to save time. Which ALCOA principle breaks? Which regulation? What CAPA?
2. **Excel calc.** QC analyst computes potency in an unlocked Excel sheet. Risks? How validate (GAMP, protected cells, test cases, audit)?
3. **Pipeline hotfix.** A data engineer edits production SQL directly to fix a mapping bug. What process was bypassed? Write the proper change-control steps.
4. **Deleted run.** HPLC injection failed OOS; analyst re-ran and deleted first result. Name the finding ("testing into compliance") and required investigation.
5. **Audit trail off.** Vendor SaaS has audit trail but admins can disable it. Is it Part 11 compliant? What to demand from vendor?
6. **PHI to LLM.** Team pastes patient notes into a public chatbot. Which laws? Alternatives?
7. **Late SAE.** A serious unexpected AE received Monday; report submitted 12 days later. Timelines? Root cause?
8. **Cross-border data.** EU trial data flows to US analytics team. GDPR mechanisms?
9. **Data migration.** Moving EDC data to a new CDMS; how validate migration (counts, checksums, sampled record compare, audit trail migration)?
10. **Inspection question.** Inspector asks: "Show me everyone who changed subject 1012's weight value and why." Describe your query + evidence.

## Warning letter reading task
Download 3 FDA warning letters (https://www.fda.gov/inspections-compliance-enforcement-and-criminal-investigations/compliance-actions-and-activities/warning-letters). Summarize: violation → regulation cited → expected remediation.

## Frameworks to structure answers
Risk (severity × likelihood × detectability) · Root cause (5 Whys, fishbone) · CAPA (correct, prevent, verify effectiveness) · Regulation → SOP → evidence.
Related: [[03-Regulatory-Compliance/Data-Integrity-ALCOA]], [[03-Regulatory-Compliance/Inspections-and-Audits]]
