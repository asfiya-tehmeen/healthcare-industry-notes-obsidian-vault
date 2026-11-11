# HL7 v2, CDA & FHIR

## Simple explanation
Hospital systems must talk to each other. **HL7** is the family of messaging standards. **FHIR** (Fast Healthcare Interoperability Resources, "fire") is the modern one: REST APIs returning JSON.

## Generations
- **HL7 v2** (1980s–now, pipe-delimited): still ~90% of hospital messaging (ADT admit/discharge, ORU lab results, ORM orders).
  `MSH|^~\&|LAB|HOSP|EHR|HOSP|202401101200||ORU^R01|123|P|2.5`
- **HL7 v3 / CDA / C-CDA**: XML clinical documents (discharge summaries).
- **FHIR R4** (R5 exists): resources + REST + JSON/XML. Mandated in US by the 21st Century Cures Act (patient access APIs).

## FHIR essentials
- **Resources**: Patient, Practitioner, Organization, Encounter, Observation, Condition, MedicationRequest, MedicationStatement, Procedure, DiagnosticReport, AllergyIntolerance, Immunization, Claim, ExplanationOfBenefit...
- **References** link resources (`"subject": {"reference": "Patient/123"}`).
- **Bundles** group resources; **Search**: `GET /Observation?patient=123&code=http://loinc.org|4548-4&date=ge2024-01-01`.
- **Profiles / Implementation Guides (IGs)**: US Core, IPS, Da Vinci (payers), SMART on FHIR (apps/auth), **Bulk FHIR** (`$export`, NDJSON) for analytics.
- **Terminology binding**: codes from LOINC/SNOMED/RxNorm.

```json
{"resourceType":"Observation","status":"final",
 "code":{"coding":[{"system":"http://loinc.org","code":"4548-4","display":"HbA1c"}]},
 "subject":{"reference":"Patient/123"},
 "valueQuantity":{"value":6.8,"unit":"%","system":"http://unitsofmeasure.org","code":"%"}}
```

## Data engineering with FHIR
Bulk export → land NDJSON in cloud storage → flatten (SQL on FHIR / Python) → OMOP or analytics tables. Libraries: `fhir.resources` (Python), HAPI FHIR (Java), Google Healthcare API, Azure Health Data Services, AWS HealthLake, Microsoft FHIR-Converter, Firely.

## Try it now (no signup)
```bash
curl "https://hapi.fhir.org/baseR4/Patient?_count=3" -H "Accept: application/fhir+json"
```

## Resources
- FHIR spec: https://hl7.org/fhir/
- Free intro: https://www.hl7.org/fhir/overview.html ; Smile Digital Health FHIR tutorials: https://smilecdr.com/docs
- HAPI public test server: https://hapi.fhir.org
- US Core IG: https://hl7.org/fhir/us/core/
- SQL on FHIR: https://sql-on-fhir.org
- Synthea synthetic patients: https://synthetichealth.github.io/synthea/
- Related: [[OMOP-CDM]], [[05-Data-Engineering/Healthcare-Data-Types]]
