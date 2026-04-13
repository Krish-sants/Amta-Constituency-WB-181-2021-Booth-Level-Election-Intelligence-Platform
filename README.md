# 🗳️ Amta Constituency (WB-181) — Booth-Level Election Intelligence Platform

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![ML](https://img.shields.io/badge/ML-XGBoost%20%7C%20RandomForest-green)](https://xgboost.readthedocs.io/)
[![Plotly](https://img.shields.io/badge/Viz-Plotly%20%7C%20Seaborn-purple)](https://plotly.com/)

---

## 📌 Project Overview

This project performs a **complete advanced-level data science analysis** on Form-20 booth-level election results from **Amta Assembly Constituency (No. 181), West Bengal**. It combines rigorous political analysis with state-of-the-art machine learning to generate insights a professional political strategist would use in a live campaign.

---

## 📂 Dataset Description

| Field | Detail |
|---|---|
| **Source** | Form-20 Official Polling Data |
| **Constituency** | Amta (WB-181), West Bengal |
| **Total Booths** | 366 polling stations |
| **Total Votes** | ~2,08,617 |
| **Candidates** | 7 (across BJP, TMC, CPI-M, INC, Independents) |
| **Columns** | 14 (Booth ID, 7 candidate vote columns, NOTA, Total, etc.) |

### Candidate → Party Mapping

| Candidate | Party |
|---|---|
| SUKANTA KUMAR PAUL | BJP |
| DEBTANU BHATTACHARYA | TMC |
| ASIT MITRA | CPI(M) |
| SANJEEB SANTRA | INC |
| DILIP KUMAR HAIT | IND-1 |
| BISWANATH DAS | IND-2 |
| RATAN CHANDRA MALICK | IND-3 |

---

## 🔑 Key Insights

1. **BJP won the constituency** with ~49.3% vote share, defeating TMC (~36.7%) by ~26,000 votes
2. **High-turnout booths strongly favour BJP** — winning ~70%+ of top-quartile turnout booths
3. **Battleground booths** (margin < 5%) represent thousands of swing votes that could decide future elections
4. **NOTA at 0.63%** signals moderate but non-negligible voter dissatisfaction
5. **Vote entropy** is the single strongest predictor of who wins a booth — more fragmented vote = BJP advantage

---

## 🤖 Machine Learning Approach

### Problem Framing
- **Task**: Multi-class Classification → Predict booth winner (BJP / TMC / Other)
- **Train/Test Split**: 75% / 25% (stratified)

### Models Trained
| Model | Description |
|---|---|
| Logistic Regression | Baseline linear classifier |
| Random Forest | Ensemble of decision trees (200 estimators) |
| XGBoost | Gradient-boosted trees (best performer) |

### Key Features Used
- Vote shares for all 7 parties (booth-level)
- Vote entropy (fragmentation index)
- Booth size (valid votes)
- NOTA percentage
- High-turnout flag (top 25th percentile)
- Two-horse race indicator (BJP+TMC ≥ 90%)

---

## 📊 Visualizations Included

- Party-wise vote totals (bar + pie)
- Booth valid-vote distribution (histogram)
- Winning margin distribution
- Correlation heatmap
- Interactive BJP vs TMC scatter (Plotly)
- Booth classification violin plots
- SHAP feature importance (XGBoost)
- Strategic priority map

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/amta-election-analysis.git
cd amta-election-analysis
```

### 2. Create Virtual Environment
```bash
python -m venv .venv
source .venv/bin/activate        # Linux/Mac
.venv\Scripts\activate           # Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook Amta_WB181_Election_Analysis.ipynb
```

---

## 📁 Project Structure

```
amta-election-analysis/
├── Amta_WB181_Election_Analysis.ipynb   ← Main notebook
├── 181_Form20_Amta.csv                  ← Raw data
├── requirements.txt                     ← Dependencies
└── README.md                            ← This file
```

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Data Wrangling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `plotly` |
| Machine Learning | `scikit-learn`, `xgboost` |
| Interpretability | `shap` |
| Notebook | `jupyter` |

---

## ⚠️ Limitations & Future Work

- **No temporal data** — multi-year swing analysis would need 2016 data
- **No demographic overlay** — caste/religion/income data would enrich the model
- **Future**: Build a Streamlit dashboard for real-time campaign intelligence

---

*Built as a portfolio-grade data science project. Analysis methodology follows professional political analytics standards.*
