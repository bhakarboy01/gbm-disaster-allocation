# 🌪️ Predictive Analytics for Disaster Resource Allocation

![Disaster Response](https://img.shields.io/badge/Disaster_Response-Predictive_Analytics-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Model-GBM_Quantile-success)

## 📌 Overview
India faces recurring extreme weather events where relief efforts often rely on reactive logistics—meaning supplies arrive only *after* a disaster peaks. 

This project shifts the paradigm from **reactive** to **proactive**. By predicting critical resource demand 7–30 days in advance, this machine-learning-driven decision support system allows NGOs and district disaster authorities to pre-position supplies effectively. 

> **Impact:** Pre-positioning supplies just 48 hours before a flood peak can reduce logistics costs by ~30% and expand beneficiary reach from 5,000 to 15,000 people on the exact same budget.

## 🎯 Focused Use Case: Coastal Odisha
This repository focuses specifically on **Coastal Odisha (2017–2024)**, targeting 5 highly vulnerable districts: *Puri, Kendrapara, Balasore, Jagatsinghpur, and Bhadrak*. The model fuses meteorological data, environmental conditions, and district-level exposure indicators to forecast relief kit demand.

## 📊 Visual Insights & Methodology

### 1. Exploratory Data Analysis (EDA)
Understanding historical weather anomalies, rainfall peaks, and historical resource demand across the 5 coastal districts.
![EDA Overview](images\eda_overview.png)

### 2. Feature Engineering & Importance
The model utilizes data from **NASA POWER weather observations**. We extracted lag features, rolling averages, and demographic weights. The feature importance plot below highlights which variables (e.g., accumulated rainfall, past incident frequency) drive the demand predictions the most.
![Feature Importance](images\feature_importance.png)

### 3. Model Comparison (GBM vs. Baseline)
We trained a **Gradient Boosting Machine (GBM) Quantile Model** to handle the non-linear, spike-heavy nature of disaster events. It was evaluated against a standard Holt-Winters baseline time-series model, showing superior capability in handling sudden peaks and communicating model uncertainty through upper and lower bounds.
![Model Comparison](images\model_comparison.png)

### 4. District Risk Mapping
A spatial representation of current and forecasted vulnerability across Coastal Odisha, enabling quick geographical triage for NGO operations managers.
![Risk Map](images\risk_map.png)

### 5. Decision Support & Resource Allocation
The ultimate output of the pipeline: translating raw ML predictions into a concrete, day-by-day resource allocation strategy. It explicitly communicates to non-technical relief coordinators *where* and *how much* to deploy based on the calculated risk scores.
![Decision Support Output](images\decision_support.png)

## 🛠️ Tech Stack & Data Sources
* **Language:** Python 3
* **Modeling:** Scikit-Learn (Gradient Boosting), Statsmodels (Holt-Winters)
* **Data Processing & Visualisation:** Pandas, NumPy, Matplotlib, Seaborn
* **Key Data Sources:** NASA POWER Weather Data (Historical Demographics & Climatic features)

## 🔮 Future Scope
* **Interactive Dashboard:** Deploy the final outputs into a Streamlit or Dash web app for zero-code usage by NGO operators.
* **Forward-Looking Signals:** Integrate the IMD (Indian Meteorological Department) API to feed real-time, forward-looking weather forecasts into the model.
* **Expanded Logistics:** Map OpenStreetMap (OSM) road accessibility to factor in supply-chain routing constraints during floods.

## 👥 Contributors
* **[Hemant Bhakar](https://www.linkedin.com/in/bhakar-hemant)**
* **[Deepak Malik](https://www.linkedin.com/in/deepak-malik-20511728b)**

*We are open to contributions! If you are a data scientist, GIS specialist, or humanitarian worker, feel free to open an issue or submit a pull request to help improve the model's accuracy or expand it to new regions.*