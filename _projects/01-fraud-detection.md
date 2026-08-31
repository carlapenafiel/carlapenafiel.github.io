---
layout: page
title: Fraud & Anomaly Detection — Banking/Insurance & Water Utilities
category: work
importance: 1
img: assets/img/fraud.jpg
tags: [ML, LightGBM, Anomaly Detection, IsolationForest, Clustering, Seasonality, NLP, BETO, Streamlit, APIs]
---

## V1 · Banking/Insurance — Fraud Probability (LightGBM + NLP)

Supervised fraud detection model using **LightGBM** on client and incident-level features, augmented with **Spanish BETO embeddings** generated from free-text incident descriptions.

- **Features:** demographics, claims history, incident metadata, device/network information, and text embeddings (BETO).
- **Model:** LightGBM supervised classification with calibrated fraud probabilities.
- **Outputs:** calibrated fraud score, ranked investigation queues, and SHAP-based explainability.
- **Dashboard:** **Streamlit** application for analysts, including threshold tuning, cohort drill-downs, and feature attributions.
- **Data model:** one row per *client–incident*, with fraud status as the target.

---

## V2 · Water Utility — Anomaly Detection, Seasonality & Early Alerts

Unsupervised and semi-supervised analytics pipeline designed to identify abnormal consumption and billing patterns, distinguish potential root causes, and anticipate preventive interventions.

### Outlier Detection

- **Consumption:** Isolation Forest, moving-average baselines, and statistical tests to identify abnormal consumption patterns.
- **Billed value:** anomaly detection to identify unusual billed amounts and potential billing-related issues.

### Seasonality

- **STL / seasonal decomposition** to identify recurring consumption patterns and distinguish seasonal behavior from abnormal observations.
- Identification of seasonal archetypes to support more accurate anomaly detection and triage.

### Clustering

- Grouped clients with similar consumption and behavioral patterns to accelerate investigation and support differentiated operational playbooks.

### Anticipation

- **Supervised model** estimating the probability of an upcoming preventive intervention (“reformas”).
- Used predictive signals from historical consumption, billing, and behavioral patterns to support early intervention.

### Dashboard

- **Streamlit** early-warning and triage application.
- Root-cause tags, prioritized alert queues, and client-level timelines.
- Designed to help operational teams move from detection to investigation and action.

---

## Technical Approach

The project combined multiple modeling paradigms depending on the business problem:

| Problem | Approach |
|---|---|
| Fraud detection | LightGBM + NLP/BETO embeddings |
| Explainability | SHAP |
| Consumption anomalies | Isolation Forest + moving averages + statistical tests |
| Billing anomalies | Statistical anomaly detection |
| Seasonality | STL / seasonal decomposition |
| Behavioral segmentation | Clustering |
| Preventive intervention prediction | Supervised learning |
| Decision support | Streamlit |

---

## Repository Highlights

Selected notebooks and scripts from the project:

### Outliers — Consumption

- `notebooks_outliers_consumo/Model_Final_MM.ipynb`
- `notebooks_outliers_consumo/Experiments_Models_Outliers.ipynb`
- `notebooks_outliers_consumo/MM_IF_Features_Model.ipynb`
- `notebooks_outliers_consumo/Modelo_Isolation_Forest.ipynb`
- `notebooks_outliers_consumo/Modelo_media_movil.ipynb`

### Outliers — Billed Value

- `notebooks_outliers_valor/Modelo_No_Outliers_Valor_Facturado.ipynb`

### Seasonality

- `notebooks_sazonalidade/MM_Seasonality_FV.ipynb`
- `notebooks_sazonalidade/Model_Seasonality_Arquetipos.ipynb`
- `notebooks_sazonalidade/Model_Seasonality_Clusterizacion_Tests.ipynb`

### Clustering

- `notebooks_clusterizacion/0_Testes_Clusterizacion.ipynb`
- `notebooks_clusterizacion/1_MM_Clusterizacion_Final.ipynb`

### Anticipation — Preventive Interventions

- `notebooks_anticipacao_reformas/1_preproc.ipynb`
- `notebooks_anticipacao_reformas/2_encode.ipynb`
- `notebooks_anticipacao_reformas/3_run_train_and_tests.ipynb`
- `notebooks_anticipacao_reformas/4_calibration.ipynb`
- `notebooks_anticipacao_reformas/6_optuna.ipynb`
- `notebooks_anticipacao_reformas/7_shap.ipynb`
- `scripts/run_preproc.py`
- `scripts/run_encode.py`
- `scripts/run_optuna.py`
- `scripts/run_train.py`

---

## Confidentiality

Client data is confidential. Public demonstrations use synthetic data designed to mirror the architecture and analytical workflow without exposing proprietary information.