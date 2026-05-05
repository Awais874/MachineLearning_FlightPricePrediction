# ✈️ Flight Ticket Price Prediction
**COM7022 — Machine Learning **

A supervised regression project predicting Indian domestic flight ticket prices using 300,153 EaseMyTrip booking records. Covers the full ML pipeline from data cleaning to model evaluation.

---

## 📊 Results

| Model | R² (%) | RMSE (Rs.) | MAE (Rs.) | MAPE (%) |
|---|---|---|---|---|
| Linear Regression | 90.61% | 6,956.58 | 4,546.00 | 40.49% |
| Ridge Regression | 90.61% | 6,956.58 | 4,546.01 | 40.49% |
| Lasso Regression | 90.61% | 6,956.55 | 4,545.94 | 40.49% |
| Decision Tree | 98.14% | 3,099.95 | 1,375.76 | 9.76% |
| **Random Forest** | **98.51%** | **2,771.51** | **1,261.92** | **8.96%** |

**Best Model:** Random Forest Regressor (OOB R² ≈ 0.98 confirms generalisation)

---

## 🔧 Pipeline

- **Cleaning** — duplicates removed, median imputation for `duration` and `days_left`, dropped rows with missing target
- **Feature Engineering** — bidirectional route pairs, duration in minutes, duration categories (≤3h / 3–7h / 7–11h / >11h), official aerial distance (km)
- **Encoding** — LabelEncoder on 9 categorical features
- **Scaling** — StandardScaler (mean=0, std=1)
- **Split** — 70% train (210,097) / 30% test (90,041), random_state=42

---

## 📈 Key Findings

- **Travel class** is the dominant predictor — Business median (Rs.63,000) is ~5–6× Economy (Rs.6,500)
- **Airline brand** creates persistent pricing tiers: Vistara (Rs.30,397 avg) vs AirAsia (Rs.4,091 avg)
- **Booking lead time** negatively correlated with price (Spearman ρ = −0.267) — prices spike within 10 days of departure
- All 7 hypothesis tests rejected H₀ at α = 0.05

---

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn openpyxl
jupyter notebook flight_price_prediction.ipynb
```
Go to **Kernel → Restart & Run All**

> ⚠️ Dataset file must be named `Flight_dataset[4039].xlsx` in the same directory as the notebook.

---

## 🛠️ Tech Stack
`Python` · `Jupyter Notebook` · `scikit-learn` · `pandas` · `seaborn` · `scipy`
