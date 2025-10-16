# Hospital-Experience-Dashboard-From-Patient-Survey-Star-Rating-Regression-1-5-
This project is based on a best in class interactive dashboard for healthcare policy and decision makers, it enables them to overview Hospital experience by patient rating across US states. The dashboard has two CMS Dataset to Patient Survey (HCAHPS) to visualise Average Patient rating 
# HCAHPS Patient Experience Dashboard
Interactive analysis and modeling of **Patient Survey Star Rating (1–5)** using CMS Hospital General Information and HCAHPS data, focusing on **hospital ownership**, **emergency service availability**, and **regional** patterns.

> **Compliance:** No PHI/PII. This repo contains code, docs, and synthetic/small sample data only. Raw CMS files should be stored outside GitHub.

---

## 📌 Project Card (for resume/portfolio)
**Patient Survey Star Rating — Regression (1–5)** — *Aug 2025*  
**Role:** Lead Analyst • **Type:** Supervised Regression, Python  
**Goal:** Predict HCAHPS star rating from hospital ownership, emergency services, and region.  
**Data:** CMS Hospital General Information + HCAHPS (joined).  
**Methods:** Linear Regression, Random Forest, Gradient Boosting; diagnostics (linearity, residual normality), multicollinearity scan, error analysis by ownership.  
**Metrics:** RMSE, MAE; feature importance for interpretability.  
**Deliverables:** Executive write-up and visuals; what-if scenarios by ownership type.  
**Stack:** Python, Matplotlib; report figures suitable for a leadership brief.

---

## 🎯 Objectives
- Build a reproducible pipeline to clean, join, and profile CMS + HCAHPS datasets.
- Explain variation in **Patient Survey Star Rating (1–5)** across ownership/regions.
- Produce leader-ready visuals and scenario analysis (“what if ownership/emergency coverage changes?”).

## 🧰 Tech Stack
Python • pandas • scikit-learn • matplotlib • (optional) Streamlit/Altair/Plotly

## 🗂️ Repository Structure
├─ notebooks/ # EDA & modeling (no raw data in Git)
├─ src/ # data loaders, cleaning, features, utils
├─ reports/ # exported charts/figures for README/briefs
├─ data/ # (empty in Git; keep real data external)
├─ requirements.txt
└─ README.md

## 📊 Data Sources
- **CMS Hospital General Information**
- **HCAHPS (Hospital Consumer Assessment of Healthcare Providers and Systems)**  
Links referenced in docs/notebooks. Download and store locally (outside Git).

## 🧹 Data Prep & QA (high-level)
- Type coercion, deduplication, standardized hospital identifiers
- Missingness scan & imputation rationale
- Range/outlier checks for star ratings and key drivers

## 🤖 Modeling
- **Target:** Patient Survey Star Rating (1–5)
- **Models:** Linear Regression, Random Forest Regressor, Gradient Boosting Regressor
- **Validation:** train/validation split (or cross-validation); residual diagnostics (linearity, normality, heteroscedasticity)
- **Explainability:** global feature importance; error analysis by ownership type; partial dependency / what-if views

## 📈 Results (replace with your actual numbers)
- Baseline metrics: RMSE / MAE
- Lift from tree-based models vs. linear baseline
- Key drivers (e.g., ownership type, region dummies, emergency services)
- What-if scenarios: estimated rating changes under different ownership/emergency-service combinations

## 🧪 Reproduce Locally
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
# open notebooks/01_eda.ipynb then notebooks/02_modeling.ipynb
