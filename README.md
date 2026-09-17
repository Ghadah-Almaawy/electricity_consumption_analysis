# Analyzing Electricity Consumption Patterns — London Smart Meters 

A big-data analytics project that explores household electricity consumption patterns using the **London Smart Meters dataset** (~5,500 households, 30-minute interval readings) and builds predictive models for energy usage, using **Apache Spark**.

> Course project — DS331: Big Data Analytics, 2025–2026 (Section 62S).
> Aligned with **UN Sustainable Development Goal 7** — Affordable and Clean Energy.
> This was a **group project**; this repository reflects my contribution to the shared codebase.

##  Problem Statement

Growing electricity demand in urban areas creates challenges for efficient energy management. Understanding consumption patterns at scale helps utilities and households plan smarter, more sustainable energy usage.

##  Objective

Analyze household-level electricity consumption at scale, uncover daily/weekly/seasonal usage trends and peak-demand periods, and build regression models that predict energy consumption from time-based features.

##  Project Workflow

1. **Data Ingestion** — loading the London Smart Meters half-hourly readings into Spark (`recursiveFileLookup` across all household files).
2. **Data Cleaning** — handling nulls, trimming, type casting.
3. **Feature Engineering** — extracting `hour`, `day of week`, and `month` from timestamps; aggregating consumption stats (mean, std).
4. **Exploratory Analysis** — visualizing daily, weekly, and seasonal consumption trends and peak-demand periods.
5. **Model Building** — training and comparing three Spark ML regressors:
   - Linear Regression
   - Random Forest Regressor
   - Gradient Boosted Trees (GBT) Regressor
6. **Model Evaluation** — RMSE, MAE, and R² for each model.

##  Results

| Model | RMSE | MAE | R² |
|---|---|---|---|
| Linear Regression | 0.2912 | 0.1687 | 0.0306 |
| Random Forest | 0.2888 | 0.1669 | 0.0466 |
| **GBT (best)** | **0.2874** | **0.1652** | **0.0558** |

Gradient Boosted Trees achieved the lowest error and highest R² among the three models, though all models show that consumption is influenced by many factors beyond simple time features — reflecting the inherent variability of individual household behavior.

##  Tech Stack

- Python
- Apache Spark (PySpark) — distributed data processing & ML
- pandas — light-weight local data handling
- matplotlib — visualization

##  Running the Project

```bash
git clone <this-repo-url>
cd electricity-consumption-analysis
pip install -r requirements.txt
jupyter notebook electricity_consumption_analysis.ipynb
```

> Note: the London Smart Meters dataset is not redistributed here due to its size. Download it from [Kaggle — Smart Meters in London](https://www.kaggle.com/datasets/jeanmidev/smart-meters-in-london) and place it in the project root before running the notebook.

## Team & Contribution

This was a group project completed as part of the DS331 Big Data Analytics course. My role focused on **[fill in your specific contribution, e.g. "feature engineering & model evaluation" or "EDA & Spark pipeline setup"]**.

##  License

This project is shared for educational and portfolio purposes.
