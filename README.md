# The Ledger: Fraud Analysis Case Study

This repository documents my investigation into a major European credit card fraud dataset. The goal here isn't just to dump code, but to demonstrate how I approach raw data, formulate hypotheses, and extract actual business value.

## Structure of the Investigation

- **notebooks/01_EDA_dan_Modeling.ipynb**
  The raw workspace containing the Python code, data transformations, and statistical modeling.

- **Step_1_Time_Analysis/**
  The first phase of the investigation. Instead of jumping straight into complex algorithms, I started by questioning the temporal nature of the crimes. Do fraudsters sleep?
  - `Analyst_Methodology_Step1_EN.md` / `_ID.md`: My thought process on why time matters and how I handled extreme data imbalance.
  - `Interactive_Report_Step1.html`: The interactive visual evidence.
  - `Advanced_Dashboard_Step1.xlsx`: The executive summary formatted for non-technical stakeholders.

## Why this matters
Real-world fraud detection is plagued by extreme data imbalance. This capstone demonstrates my ability to handle feature engineering and translate anomalies into actionable security policies (like the *Night-Watch Protocol*).

- **Step_2_Amount_Analysis/**
  The second phase uncovers 'The Middle-Ground Anomaly'. Fraudsters intentionally cap their theft at medium amounts ($100-$2000) to evade hard-limit bank sensors. Contains interactive Boxplots and methodology SVGs.
