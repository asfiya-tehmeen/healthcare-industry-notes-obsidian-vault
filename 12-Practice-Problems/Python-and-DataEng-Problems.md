# Python, Coding, Data Engineering & Automation Problems

## Coding practice (interview style)
- LeetCode Top Interview 150: https://leetcode.com/studyplan/top-interview-150/
- NeetCode roadmap (curated): https://neetcode.io/roadmap
- HackerRank Python: https://www.hackerrank.com/domains/python
- Codewars: https://www.codewars.com

Key problems & healthcare analog
| Problem | Analog |
|---|---|
| [Two Sum](https://leetcode.com/problems/two-sum/) | match lab IDs in two files |
| [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) | validate nested XML/HL7 segments |
| [Merge Intervals](https://leetcode.com/problems/merge-intervals/) | merge overlapping drug exposure periods |
| [Group Anagrams](https://leetcode.com/problems/group-anagrams/) | group name variants for patient matching |
| [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) | most frequent adverse events |
| [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) | longest streak of therapy days |
| [LRU Cache](https://leetcode.com/problems/lru-cache/) | caching code lookups |
| [Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/) | versioned records / audit trail |
| [Insert Interval](https://leetcode.com/problems/insert-interval/) | insert new visit window |
| [Design Hit Counter](https://leetcode.com/problems/design-hit-counter/) | rate-limiting API calls |
| [Word Break](https://leetcode.com/problems/word-break/) | tokenize concatenated drug names |
| [Edit Distance](https://leetcode.com/problems/edit-distance/) | fuzzy match drug/patient names |

## Pandas / data wrangling
- Pandas exercises: https://github.com/guipsamora/pandas_exercises
- Kaggle Learn Pandas & Data Cleaning: https://www.kaggle.com/learn
- 100 pandas puzzles: https://github.com/ajcr/100-pandas-puzzles
- Real data: [[13-Resources/Datasets]]

## Data engineering practice
- Data Engineering Zoomcamp (hands-on project): https://github.com/DataTalksClub/data-engineering-zoomcamp
- DataExpert / Start Data Engineering: https://www.startdataengineering.com
- dbt Fundamentals: https://learn.getdbt.com
- Airflow tutorial: https://airflow.apache.org/docs/apache-airflow/stable/tutorial/
- Spark practice (PySpark): https://spark.apache.org/docs/latest/api/python/getting_started/
- Snowflake free trial hands-on: https://quickstarts.snowflake.com
- Databricks Free Edition: https://www.databricks.com/learn/free-edition
- System design for data: *Designing Data-Intensive Applications*

## Automation / scripting problems (do these, push to GitHub)
1. **ClinicalTrials.gov API → SQLite** nightly (https://clinicaltrials.gov/data-api/api).
2. **openFDA**: pull top adverse events per drug via https://api.fda.gov/drug/event.json?search=patient.drug.medicinalproduct:"ibuprofen"&count=patient.reaction.reactionmeddrapt.exact
3. **DailyMed** SPL XML parse → extract boxed warnings.
4. **HL7 v2 parser**: read ORU messages, output CSV (try `hl7` Python lib).
5. **FHIR bulk NDJSON flattener** to Parquet using DuckDB.
6. **Excel report automation** with openpyxl for weekly KPI.
7. **Folder watcher** that checksums incoming files (SHA-256) and logs to audit table.
8. **SDTM checker**: verify required variables & ISO 8601 dates.
9. **PDF table extraction** (pdfplumber) from FDA label.
10. **Email → ticket classification** with simple NLP.

## Data modeling exercises
- Design schema for a clinical trial (study, site, subject, visit, form, audit).
- Design a slowly changing dimension (SCD2) for HCP master data.
- Model OMOP ETL for 2 source systems.
- Design an audit trail that satisfies Part 11.

## Stats/analytics problems
- Kaggle: Heart disease, diabetes, "Medical Cost", MIMIC demo — https://www.kaggle.com/datasets (search)
- Kaplan–Meier on lung dataset (R `survival`, Python `lifelines` docs): https://lifelines.readthedocs.io
- A/B test & sample size: https://www.evanmiller.org/ab-testing/

## Competitions
- Kaggle healthcare comps: https://www.kaggle.com/competitions
- DrivenData health challenges: https://www.drivendata.org/competitions/
- PhysioNet challenges: https://physionet.org/challenges/
- Related: [[SQL-Problems]], [[11-Tech-Automation-AI/Automation-in-Pharma]]
