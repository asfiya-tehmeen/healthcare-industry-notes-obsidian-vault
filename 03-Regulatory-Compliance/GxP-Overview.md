# GxP Overview

## Simple explanation
"GxP" = the family of "Good ___ Practice" rules. The x is a placeholder. They exist so that you can **prove** a product is safe and data is reliable. Golden rule: **"If it isn't documented, it didn't happen."**

| Rule | Area | Applies to | Example thing |
|---|---|---|---|
| GLP | Laboratory | preclinical tox studies | study director, raw data retention |
| GCP | Clinical | trials | informed consent, source data verification |
| GMP / cGMP | Manufacturing | making drugs | batch records, cleanrooms |
| GDP | Distribution | storage/transport | cold chain, temperature logs |
| GVP | Vigilance | safety monitoring | adverse event reporting timelines |
| GPvP, GAMP, GRP | PV, automation, review practice | |  |

## Common GxP building blocks
- **SOPs** – written procedures people follow.
- **Training records** – prove staff are qualified.
- **Change control** – no change to a validated process/system without assessment + approval.
- **Deviation / CAPA** – record unplanned events, find root cause, fix.
- **Document control** – versioned, approved, effective-dated documents.
- **Quality Management System (QMS)** – umbrella (ICH Q10).
- **Risk management** – ICH Q9; assess severity × probability × detectability (FMEA).
- **Audit trail & e-signatures** – [[21-CFR-Part-11]].
- **Data integrity** – [[Data-Integrity-ALCOA]].

## Why data people care
Any database, pipeline, report or dashboard that supports a GxP decision is a **GxP system** → must be validated, access-controlled, backed up, and change-controlled. A sloppy cron job that changes trial data could trigger a regulatory finding.

## "GxP-relevant?" quick test
Does the system's output affect product quality, patient safety, or data integrity of regulated records? If yes → GxP.

## Resources
- ISPE GAMP 5 (2nd ed.) – https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition
- FDA CGMP: https://www.fda.gov/drugs/pharmaceutical-quality-resources/current-good-manufacturing-practice-cgmp-regulations
- Next: [[Computer-System-Validation]]
