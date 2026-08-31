---
layout: page
title: Pricing & Elasticity — Chemicals, Gas & Insurance
category: work
img: assets/img/pricing.jpg
importance: 2
tags: [Pricing, Elasticity, Forecasting, Optimization, Pyomo, LightGBM, Scenario Planning, NLP, Streamlit]
---

## Overview

Built **price–demand elasticity models** and **price recommenders** to simulate scenarios and forecast demand, revenue, and margin across chemicals, gas, and insurance.

The work combined statistical and machine learning models with scenario analysis and optimization to translate pricing decisions into expected commercial outcomes.

- **Outputs:** recommended prices and expected volume, revenue, and margin by segment.
- **Dashboard:** **Streamlit** scenario explorer allowing users to modify price and cost assumptions and evaluate the resulting business impact.
- **Decision support:** scenario-based recommendations designed for business users and commercial teams.

---

## Elasticity & Price Recommender

The general modeling workflow consisted of:

1. **Estimate price–demand elasticity** by product or segment, accounting for non-linear relationships, seasonality, and relevant shocks.

2. **Simulate price and cost scenarios** and estimate their impact on demand, revenue, and margin.

3. **Optimize pricing decisions** subject to relevant business constraints, including capacity and renewal-rate targets.

4. **Serve results to business users** through **Streamlit** applications and APIs.

---

## Insurance Pricing — Individualized Elasticity & Optimization

A pricing framework combining machine learning and mathematical optimization to estimate individualized renewal responses to price changes and identify margin-maximizing pricing decisions.

### Data Preparation

- `limpieza_datos` (**data cleaning**): joins policies, customers, vehicles, and claims data.
- `imputar_valores` (**value imputation**): imputes prices for non-renewals using business rules and claims information.

### Elasticity Model

- `modelo_elasticidad` (**elasticity model**): **LightGBM** model estimating renewal probability as a function of **price delta** and client-level covariates.
- Features included claims, vehicle, and customer characteristics.
- The model allows renewal probability to be evaluated under different price scenarios.

### Price Scenarios

- `variacion_precios` (**price variation**): simulates price changes from **–50% to +50%**, in 10% increments.
- Estimates individualized renewal probability under each scenario.

### Optimization

- `optimizacion` (**optimization**): **Pyomo** binary optimization model.
- Objective: **maximize total portfolio margin**.
- Constraint: maintain the portfolio renewal rate within the **80–85% target range**.

### Results

- `resultados` (**results**): tables, descriptive statistics, and scenario summaries used to communicate pricing recommendations and expected commercial impacts.

### NLP

- **NLP usage:** text-derived signals were incorporated as model features where available.

---

## Where Applied

### Chemical Company

Portfolio pricing and elasticity analysis by SKU and segment.

### Gas Company

Price forecasting using external drivers and elasticity-informed pricing recommendations.

### Insurance

Individualized renewal elasticity modeling combined with margin optimization.

---

## Technical Approach

| Problem | Approach |
|---|---|
| Price–demand relationship | Elasticity modeling |
| Non-linear relationships | Machine learning |
| Renewal probability | LightGBM |
| Price scenarios | Scenario simulation |
| Portfolio pricing | Pyomo optimization |
| Commercial constraints | Capacity / renewal-rate targets |
| Text signals | NLP |
| Decision support | Streamlit |
| Deployment | APIs |

---

## Confidentiality

Client data is confidential. Public demonstrations use synthetic data designed to mirror the modeling workflow without exposing proprietary information.