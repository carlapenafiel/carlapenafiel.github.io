---
layout: page
title:  Fraud & Anomaly Detection — Banking/Insurance & Water Utilities
category: work
importance: 1
tags: [ML, LightGBM, Anomaly Detection, IsolationForest, Clustering, Seasonality, NLP, BETO, Streamlit, APIs]
---

**V1 · Banking/Insurance — Fraud Probability (LightGBM + NLP)**  
Supervised fraud model using **LightGBM** on client & incident features, augmented with **Spanish BETO embeddings** from free-text incident descriptions.  
- **Features:** demographics, claims history, incident metadata, device/network, text embeddings (BETO).  
- **Outputs:** calibrated fraud score, ranked review queues, SHAP explainability.  
- **Dashboard:** **Streamlit** app for analysts (threshold tuning, cohort drill-downs, feature attributions).  
- **Data model:** one row per *client–incident*, fraud label as target.

**V2 · Water Utility — Outliers, Seasonality, Clustering & Early Alerts**  
Unsupervised/semi-supervised pipeline to triage claim root-cause (consumption vs. billing vs. seasonality vs. frequent claimer).  
- **Outliers (consumption & billed value):** Isolation Forest, moving-average baselines, statistical tests.  
- **Seasonality:** STL/seasonal decomposition to flag seasonal archetypes.  
- **Clustering:** group similar behaviors to speed up triage and playbooks.  
- **Anticipation (supervised):** probability of upcoming “reformas” (preventive actions).  
- **Dashboard:** **Streamlit** early-warning & triage (root-cause tags, alert queues, client timelines).

**Repository highlights (selected notebooks & structure)**  
- *Outliers — Consumo:* `notebooks_outliers_consumo/Model_Final_MM.ipynb`, `Experiments_Models_Outliers.ipynb`, `MM_IF_Features_Model.ipynb`, `Modelo_Isolation_Forest.ipynb`, `Modelo_media_movil.ipynb`  
- *Outliers — Valor:* `notebooks_outliers_valor/Modelo_No_Outliers_Valor_Facturado.ipynb`  
- *Seasonality:* `notebooks_sazonalidade/MM_Seasonality_FV.ipynb`, `Model_Seasonality_Arquetipos.ipynb`, `Model_Seasonality_Clusterizacion_Tests.ipynb`  
- *Clustering:* `notebooks_clusterizacion/0_Testes_Clusterizacion.ipynb`, `1_MM_Clusterizacion_Final.ipynb`  
- *Anticipation:* `notebooks_anticipacao_reformas/1_preproc.ipynb`, `2_encode.ipynb`, `3_run_train_and_tests.ipynb`, `4_calibration.ipynb`, `6_optuna.ipynb`, `7_shap.ipynb`; `scripts/run_preproc.py`, `run_encode.py`, `run_optuna.py`, `run_train.py`

*Note:* client data is confidential; public demos use synthetic data mirroring the architecture.
