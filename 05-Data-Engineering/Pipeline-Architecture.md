# Pipeline Architecture for Regulated Data

## Reference architecture
```
Sources (EDC, EHR/FHIR, claims files, LIMS, APIs, SFTP)
   │  ingestion (batch/stream; CDC; Airbyte/Fivetran/ADF/Glue/Kafka)
   ▼
RAW / Bronze (immutable, as-received, checksummed, retention)
   ▼  cleaning, standardization, de-dup, code mapping
STANDARDIZED / Silver (CDISC, OMOP, FHIR-flat)
   ▼  business logic, aggregates, derivations
CURATED / Gold (marts, ADaM, KPI tables, feature store)
   ▼
Consumption: BI (Tableau/Power BI), notebooks, SAS/R stats env, APIs, regulatory submissions
Cross-cutting: catalog & lineage, DQ tests, orchestration, secrets, IAM, audit logging, monitoring, DR
```

## Tool landscape
- Cloud: AWS (S3, Glue, Redshift, HealthLake, Athena), Azure (ADF, Synapse, Fabric, Health Data Services), GCP (BigQuery, Healthcare API).
- Warehouses/lakehouses: **Snowflake**, **Databricks**, Redshift, BigQuery.
- Orchestration: **Airflow**, Dagster, Prefect, ADF.
- Transformation: **dbt**, Spark/PySpark, SQL.
- Catalog/lineage: Collibra, Alation, DataHub, OpenLineage, Unity Catalog.
- Pharma-specific: Palantir Foundry, Veeva Vault CDMS, Medidata Clinical Data Studio, SAS Viya, Domino/Posit (SCE – Statistical Computing Environment).

## GxP design principles
1. **Immutability & traceability** – never overwrite raw; version everything (data, code, config).
2. **Idempotent** jobs, deterministic outputs → reproducible results (important for submissions).
3. **Separation of environments**: dev → test(validation) → prod; promotions via change control.
4. **Least-privilege access**, service accounts, no hard-coded secrets.
5. **Automated testing as validation evidence** (dbt tests, pytest, row-count reconciliation).
6. **Audit logging** of pipeline runs, parameters, user, code version (git SHA).
7. **Data contracts** with providers (schema, SLA, units).
8. **Backups & DR tested**.
9. **Documentation**: data dictionary, lineage diagram, SOPs.

## Batch vs streaming
Most pharma is batch (nightly EDC extracts, daily claims). Streaming for IoT in manufacturing, near-real-time safety triage, ADT feeds.

## Example Airflow DAG skeleton
```python
from airflow import DAG
from airflow.operators.python import PythonOperator
from datetime import datetime
with DAG("edc_to_sdtm", start_date=datetime(2024,1,1), schedule="@daily", catchup=False) as dag:
    extract = PythonOperator(task_id="extract_edc", python_callable=extract_fn)
    validate_raw = PythonOperator(task_id="validate_raw", python_callable=dq_fn)
    sdtm = PythonOperator(task_id="build_sdtm", python_callable=sdtm_fn)
    p21 = PythonOperator(task_id="conformance_check", python_callable=p21_fn)
    extract >> validate_raw >> sdtm >> p21
```

## Resources
- Data Engineering Zoomcamp (free): https://github.com/DataTalksClub/data-engineering-zoomcamp
- dbt Learn: https://learn.getdbt.com
- Airflow docs: https://airflow.apache.org/docs/
- Designing Data-Intensive Applications (book) – [[13-Resources/Books]]
- Related: [[Data-Quality-and-Validation]], [[De-identification-and-Security]]
