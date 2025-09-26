---
layout: project
title: Pricing & Elasticity — Chemicals, Gas & Insurance
category: work
importance: 2
tags: [Pricing, Elasticity, Forecasting, Optimization, Pyomo, LightGBM, Scenario Planning, NLP, Streamlit]
# image: /assets/img/projects/pricing.jpg  # (optional)
---

**Overview**  
Built **price–demand elasticity models** and a **price recommender** to simulate scenarios and forecast demand, revenue, and margin across chemicals, gas, and insurance.  
- **Dashboard:** **Streamlit** scenario explorer (±% price, costs, demand shifts) with recommended price & expected **volume/revenue/margin** per segment.

**Elasticity & Price Recommender (general approach)**  
1) Estimate elasticity by product/segment (non-linear curves; seasonality/shocks).  
2) Simulate price/cost scenarios; compute demand & margin impacts.  
3) Optimize price vs. constraints (capacity/renewal targets).  
4) Serve results to business via **Streamlit** + API.

**Insurance Pricing — repository workflow (first version)**  
- `limpieza_datos` (**data_cleaning**): joins policies, customers, vehicles, claims.  
- `imputar_valores` (**value_imputation**): imputes prices for non-renewals using business rules & claims info.  
- `modelo_elasticidad` (**elasticity_model**): **LightGBM** to learn renewal probability vs. **price delta** and covariates (claims, vehicle, customer).  
- `variacion_precios` (**price_variation**): simulate price from **–50% to +50%** (steps of 10%) and infer renewal probability per client.  
- `optimizacion` (**optimization**): **Pyomo** binary optimization to **maximize total margin** with a **renewal-rate constraint (80–85%)**.  
- `resultados` (**results**): tables, descriptive stats, and scenario summaries for presentation.  
- **NLP usage:** text signals embedded as features where available.

**Where applied**  
- **Chemical company:** portfolio pricing & elasticity by SKU/segment.  
- **Gas company:** price forecasting with external drivers and elasticity-informed recommendations.  
- **Insurance:** individualized renewal elasticity + margin optimization.

*Note:* client data is confidential; synthetic demos mirror the modeling steps and UI.
