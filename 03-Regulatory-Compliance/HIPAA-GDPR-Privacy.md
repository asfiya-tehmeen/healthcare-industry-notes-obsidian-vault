# Health Data Privacy: HIPAA, GDPR, DPDP & more

## Simple explanation
Health data is the most sensitive personal data. Laws say who may see it, what you can do with it, and what happens on a breach.

## HIPAA (US)
- Applies to **Covered Entities** (providers, health plans, clearinghouses) and **Business Associates** (vendors handling PHI – sign a **BAA**).
- **Privacy Rule** – permitted uses/disclosures, minimum necessary.
- **Security Rule** – administrative, physical, technical safeguards (encryption, access control, audit logs).
- **Breach Notification Rule** – notify individuals/HHS within 60 days.
- **18 identifiers** to remove for **Safe Harbor** de-identification: names, geographic units smaller than state, all date elements except year (and ages >89), phone, email, SSN, MRN, plan ID, account no., licence, vehicle IDs, device IDs, URLs, IPs, biometrics, photos, any other unique code.
- **Expert Determination** – statistician certifies very small re-ID risk.
- **Limited Data Set** – keeps dates/zip, needs data use agreement.
- Info: https://www.hhs.gov/hipaa/index.html

## GDPR (EU/UK)
- Health, genetic, biometric = **special category data**; needs explicit legal basis (consent or research exemption etc.).
- Principles: lawfulness, purpose limitation, minimisation, accuracy, storage limitation, integrity/confidentiality, accountability.
- Rights: access, rectification, erasure, portability, objection.
- **Pseudonymisation** (still personal data) vs **anonymisation** (not).
- **DPIA** required for high-risk processing; **DPO** appointments; breach notice within 72 h; fines up to 4% global turnover.
- Cross-border transfers: SCCs, adequacy decisions.
- Text: https://gdpr-info.eu

## Others
- **India DPDP Act 2023**, **CCPA/CPRA** (California), **PIPL** (China), **LGPD** (Brazil), **PHIPA** (Ontario).
- **42 CFR Part 2** (substance-use records), **GINA** (genetic), **FERPA** n/a.
- Clinical trials: ICH-GCP confidentiality + GDPR informed consent.

## Technical privacy toolkit
- Tokenization / hashing with salt; k-anonymity; date shifting; generalization (age bands, 3-digit zip)
- Encryption at rest (AES-256) and in transit (TLS)
- Column-level security, dynamic masking (Snowflake masking policies, Databricks Unity Catalog)
- Consent management, data retention schedules, DSAR workflows
- Data Processing Agreements; vendor risk assessment

## Mini-exercise
Given table patient(name, dob, zip, diagnosis, visit_date), write the Safe Harbor-compliant view: drop name; dob→year (age band if >89); zip→first 3 digits (only if population >20k); visit_date→year or shifted by patient-specific random offset (note: shifting is for limited/expert methods, not Safe Harbor).

## Resources
- HHS de-identification guidance: https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html
- ICO UK GDPR guide: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/
- Related: [[05-Data-Engineering/De-identification-and-Security]]
