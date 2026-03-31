# 📡 Telecom Customer Churn Analysis with Apache Spark

Analysis of customer churn behavior in a telecommunications provider using **Apache Spark**, including exploratory data analysis with **Spark SQL** and a regression model built with **MLlib**.

---

## 📌 Project Overview

This project processes a dataset of **10,000 telecom customers** to:
- Identify behavioral patterns that lead to customer churn
- Analyze churn rates across contract types, service bundles, and geographic regions
- Build a **Decision Tree Regressor** to predict monthly charges

> **Course:** Big Data Analysis — University of Macedonia, Dept. of Applied Informatics (2025–2026)  
> **Team:** Panagiotidis Theodoros, Bliona Aliki

---

## 🗂️ Repository Structure

```
telecom-churn-spark/
│
├── telecom_churn_hw2.ipynb   # Main notebook (PySpark, Spark SQL, MLlib)
├── README.md                 # Project documentation
└── report/
    └── report.pdf            # Full technical report (Greek)
```

> ⚠️ **Note:** The dataset file `telecom_churn_10k.csv` is not included in this repository due to size constraints. The notebook expects it to be uploaded to Google Colab before execution.

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Apache Spark (PySpark) | Distributed data processing |
| Spark SQL | Exploratory analysis & churn queries |
| Spark MLlib | Decision Tree Regressor |
| Matplotlib | Data visualization |
| Google Colab | Development environment |

---

## 📊 Key Findings

### Churn by Contract Type
| Contract | Churn Rate |
|----------|-----------|
| Month-to-month | ~53% |
| One year | ~21% |
| Two year | ~14% |

### Churn by Number of Services
| Services | Churn Rate |
|----------|-----------|
| 0 | ~43% |
| 1 | ~48% |
| 2 | ~37% |
| 3 | ~25% |

**Key insight:** Customers with longer commitments and more bundled services are significantly less likely to churn.

---

## 🤖 ML Model — Decision Tree Regressor

**Goal:** Predict `MONTHLY_CHARGES` (continuous variable)

**Features used:**
- Categorical: `CONTRACT_TYPE`, `PAYMENT_METHOD`, `COUNTRY` (encoded with StringIndexer)
- Numerical: `AGE`, `TENURE_MONTHS`, `NUM_COMPLAINTS`, `SUPPORT_CALLS`, `HAS_INTERNET`, `HAS_MOBILE`, `HAS_TV`, `NUM_SERVICES`

**Results (on 30% test set):**
| Metric | Value |
|--------|-------|
| RMSE | 7.95 € |
| R² | 0.5052 |
| Relative Error | ~22% |

**Conclusion:** The model is suitable as a decision-support tool for revenue estimation, but not for precise billing automation.

---

## 🚀 How to Run

1. Open [Google Colab](https://colab.research.google.com/)
2. Upload `telecom_churn_hw2.ipynb`
3. Upload the dataset file `telecom_churn_10k.csv` to the Colab session
4. Run all cells sequentially

> PySpark is installed automatically via the first notebook cell.

---

## 👩‍💻 My Contribution

- Data visualization (churn bar charts by contract, services, geography)
- ML modeling: feature engineering, Decision Tree Regressor training & evaluation
- Technical report writing and business analysis of results
