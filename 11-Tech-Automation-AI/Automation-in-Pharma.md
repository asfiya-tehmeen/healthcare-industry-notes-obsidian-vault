# Automation & AI in Pharma/Healthcare

## Where automation helps (high-value use cases)
| Area | Use case | Tech |
|---|---|---|
| Clinical data mgmt | auto edit checks, query generation, SDTM mapping | Python/SQL, rules engines |
| Biostat programming | TLF generation, validation compare | R/pharmaverse, SAS macros |
| Regulatory | eCTD assembly, document QC, label comparison | RPA, NLP |
| PV | case intake from email/PDF, auto-coding, duplicate detection, narratives | OCR + LLM + rules |
| Quality | CAPA trending, doc review, deviation classification | NLP/classification |
| Compliance | access reviews, audit-trail reviews, SOP gap checks | scripts, SIEM |
| Manufacturing | predictive maintenance, batch anomaly detection | ML/time series |
| Commercial | HCP targeting, forecasting, NBA | ML |
| Discovery | molecule property prediction, protein structure (AlphaFold) | deep learning |
| Healthcare ops | prior auth, coding assist, claims denial prediction | NLP |

## Python/SQL automation toolbox
`pandas`, `polars`, `sqlalchemy`, `requests`, `pdfplumber`/`PyMuPDF`, `openpyxl`, `lxml` (Define-XML/E2B), `pytest`, `typer` CLIs, `schedule`/cron/Airflow, GitHub Actions, `great_expectations`, `Selenium/Playwright` for legacy UI, UiPath/Power Automate for RPA.

## Validating automation (GxP)
Script that touches regulated data → treat as system: requirements, version control, peer review, tests, change control, access control, logs. **GAMP category 5** for custom code.

## AI/LLM in regulated settings
- Risks: hallucination, non-determinism, data leakage (PHI to external APIs!), bias, explainability.
- Controls: human-in-the-loop, grounded retrieval (RAG) on approved docs, prompts/outputs logged, model/version pinning, evaluation sets, red-teaming, BAA/zero-retention vendor terms.
- Frameworks: FDA AI/ML-enabled device guidance & PCCP, **EMA reflection paper on AI**, **EU AI Act**, **NIST AI RMF**, **GAMP AI Guide (ISPE, 2025)**, **FDA draft guidance on AI to support regulatory decision-making for drugs**, CSA.
- Healthcare NLP: ClinicalBERT, spaCy/scispaCy, AWS Comprehend Medical, Google MedLM.

## Automation mini-projects
1. Script to scrape ClinicalTrials.gov API nightly into SQLite, flag new Phase 3 in your disease area.
2. PDF label parser → extract contraindications table from DailyMed SPL XML.
3. Audit-trail reviewer: flag after-hours edits, mass changes, shared-IP logins.
4. SDTM conformance checker in Python (required variables, controlled terminology).

## Resources
- Automate the Boring Stuff: https://automatetheboringstuff.com
- openFDA APIs: https://open.fda.gov/apis/
- scispaCy: https://allenai.github.io/scispacy/
- NIST AI RMF: https://www.nist.gov/itl/ai-risk-management-framework
- Related: [[03-Regulatory-Compliance/Computer-System-Validation]]
