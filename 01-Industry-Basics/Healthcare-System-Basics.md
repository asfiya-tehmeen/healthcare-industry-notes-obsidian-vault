# Healthcare System Basics

## Simple explanation
Healthcare = **providers** (give care) + **payers** (pay for it) + **patients** + **suppliers** (drugs, devices) + **regulators**. Money and data move between all of them.

## The parties
- **Providers**: hospitals, clinics, physicians, labs, pharmacies.
- **Payers**: government (Medicare, Medicaid in US; NHS in UK) and private insurers (UnitedHealth, Anthem/Elevance, Cigna, Aetna/CVS).
- **Suppliers**: pharma, devices, distributors.
- **Intermediaries**: PBMs, clearinghouses, GPOs.

## US key programs
- **Medicare** – 65+ and disabled. Parts A (hospital), B (outpatient), C (Advantage – private), D (drugs).
- **Medicaid** – low-income, state-run.
- **ACA exchanges** – individual insurance.
- **340B** – discounted drugs for safety-net providers (big analytics/compliance topic).

## How a claim works
Patient visit → provider codes it (ICD-10 diagnosis, CPT procedure) → claim (837 format) sent via clearinghouse → payer adjudicates → pays/denies → remittance (835). See [[10-Healthcare-Delivery/EHR-and-Billing]] and [[06-Analytics/Claims-Analytics]].

## Other countries (quick view)
- UK: NHS single payer; NICE decides cost-effectiveness.
- Germany: statutory insurance + AMNOG price negotiation.
- India: mixed; large generics industry; CDSCO regulator; Ayushman Bharat scheme.
- Single-payer vs multi-payer changes how pricing and data work.

## Value-based care
Pay for outcomes, not volume. Needs lots of quality metrics (HEDIS, Star ratings) → analytics jobs.

## Resources
- KFF health policy primers: https://www.kff.org
- CMS: https://www.cms.gov
- Book: *An American Sickness* (Rosenthal) – see [[13-Resources/Books]]
