# Commercial & Sales Analytics (Pharma)

## Simple explanation
How do we find the right doctors/patients, measure what's selling, and spend marketing money wisely?

## Data sources
- **Rx data** (IQVIA Xponent/NPA, Symphony): scripts by prescriber, plan, geography.
- **Sales/shipments** (867/852 wholesaler data), **claims**, **CRM** (Veeva CRM: calls, samples, emails), **HCP master data** (NPI, specialty), **payer formulary** data, **speaker programs**, **digital engagement**.

## Key terms
- **TRx / NRx / NBRx** – total / new / new-to-brand prescriptions. **Market share**, **share of voice**.
- **Decile** targeting – rank HCPs by potential.
- **Call plan / segmentation / targeting**; **next-best-action (NBA)**.
- **Field force effectiveness**, **sales force sizing**, **territory alignment**.
- **Forecasting**: patient-based (epidemiology funnel) vs trend; launch curves.
- **Marketing mix modeling**, attribution.
- **Patient journey / funnel**: diagnosed → treated → persistent.
- **Gross-to-net (GTN)**, **rebates**, **chargebacks**, **copay assistance**.
- **Sunshine Act / Open Payments** compliance: report payments to HCPs. https://openpaymentsdata.cms.gov

## Compliance angle
Promotional materials must be approved (**MLR review**: Medical-Legal-Regulatory), no off-label promotion, anti-kickback, aggregate spend reporting, consent for HCP marketing (GDPR/CAN-SPAM), PhRMA code.

## Typical SQL/BI tasks
- Territory sales trend, YoY growth, rolling 13-week TRx
- HCP segmentation (RFM-style)
- Calls → Rx lift analysis
- Master data dedupe of HCP records (MDM)

## Resources
- Open Payments data: https://openpaymentsdata.cms.gov
- Medicare Part D prescribers (practice dataset): https://data.cms.gov/provider-summary-by-type-of-service/medicare-part-d-prescribers
- ZS / IQVIA blog posts; Pharmaceutical Commerce magazine
- Related: [[07-Commercial-Market-Access/Pharma-Commercial-101]]
