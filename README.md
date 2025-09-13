# Google Merchandise Store Analysis — Drivers of Conversion & Bounce

**Objective.** Analyze Google Merchandise Store (GMS) web sessions to (1) quantify holiday effects on conversion, and (2) build reliable classifiers for **purchase** and **bounce** under class imbalance.

**Data.** Public **Google Analytics Sample (GMS)** tables in BigQuery (legacy UA). Analysis window: **2016-08-01 to 2017-06-30** across daily `ga_sessions_*` tables.  
*Note:* Sample data is anonymized/obfuscated by Google for privacy; results approximate the real store.

**Reproducible Environment.**
- R project pinned with `{renv}` (R packages recorded in `renv.lock`).
- Optional pipeline with `{targets}` for end-to-end rebuilds.

**How to Run (quick start)**
```r
# from R console in the project root
install.packages("renv")      # one time
renv::restore()               # reproduces the package environment
# If using {targets}:
install.packages("targets")   # one time
targets::tar_make()           # builds data → features → models → report
(If applicable) BigQuery extract used for raw sessions (example)

sql
Copy code
-- Replace with your exact query if different
SELECT
  fullVisitorId, visitId, visitNumber, visitStartTime,
  device.*, geoNetwork.*, trafficSource.*, totals.*, hits.*
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_*`
WHERE _TABLE_SUFFIX BETWEEN '20160801' AND '20170630';
Modeling & Evaluation

Split by visitor (not by session) to avoid leakage across train/test.

Purchase model: regularized logistic regression (elastic net glmnet).

Report ROC AUC and PR AUC (class imbalance aware), plus a confusion matrix at a stated threshold (chosen on validation by F1 or Youden’s J). Avoid accuracy as a headline metric.

Provide a calibration plot and baseline comparisons (e.g., predict-all-negative).

Key Results (fill these in with your numbers)

Purchase model: ROC AUC = ..., PR AUC = ..., threshold = ..., F1 = ....

Bounce model (if included): ROC AUC = ..., PR AUC = ....

Holiday effect: uplift window around ... days before ... with ... (method: distributed-lag / event-study).

Repository Structure

bash
Copy code
.
├─ analysis/           # Rmd/Quarto notebooks (EDA, holiday, modeling)
├─ R/                  # R functions (feature engineering, metrics, modeling)
├─ data/
│  ├─ raw/             # source extracts (ignored by git)
│  └─ processed/       # derived datasets
├─ models/             # saved model objects
├─ reports/            # final report(s), figures
├─ renv.lock
├─ _targets.R          # (optional) pipeline entrypoint
└─ .github/workflows/  # (optional) CI config
Caveats

GMS sample ≠ production GA data; conclusions are illustrative.

No PII; channel/device bias and seasonality may remain.

Citation & License

See CITATION.cff and LICENSE in the repository root.
