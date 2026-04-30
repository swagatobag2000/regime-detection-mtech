# 📊 Regime Detection in Indian Financial Markets using Deep Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Status](https://img.shields.io/badge/Status-Phase%2001%20Complete-success)
![Domain](https://img.shields.io/badge/Domain-Finance%20%7C%20AI-orange)
![Data](https://img.shields.io/badge/Data-2000--2026-informational)
![Model](https://img.shields.io/badge/Models-ML%20%2B%20DL-purple)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 🚀 Project Overview

This project builds a **multi-source intelligence system** to detect **market regimes and volatility patterns** in Indian financial markets.

Instead of relying only on price data, this system integrates:

* 📈 Market microstructure (OHLCV)
* 🌍 Geopolitical risk signals
* 📰 News sentiment (FinBERT)
* 🏛️ Economic & policy events
* 📉 Macroeconomic indicators

👉 The objective is to move from **price-based prediction → context-aware regime detection**.

---

## 🧠 Why This Project is Different

Most trading or prediction systems:

* Only use price/technical indicators
* Ignore macro + geopolitical context

This project:

* Combines **5 independent signal layers**
* Builds a **314-month feature matrix (2000–2026)**
* Uses **NLP + macroeconomics + event-driven modeling**
* Designed for **institutional-grade analysis**

---

## 🏗️ System Architecture (Conceptual)

💡 Interpretation:

* Each data source captures a **different dimension of risk**
* Final model learns **hidden interactions across domains**

---

## 📂 Project Structure (Detailed with Explanation)

```
📂 Regime_Detection_Swagato_M25AI2107/
│̨̨̨
├── README.md                                   # README.md file created for navigation
├── README.pdf                                  # PDF version of README.md file
├── requirements.txt                            # python library needed in this project
├── config.yaml                                 # if required later will see
│
├── 📂 Code/
│   ├── Phase01A_Index_Data_Setup.ipynb         # Market data collection
│   ├── Phase01A_GPR_News_Sentiment.ipynb       # News ingestion, GPR + macro + events
│   ├── Phase02A_Index_EDA_Cleaning.ipynb
│   ├── Phase02B_GPR_EDA_Cleaning.ipynb
│
├── 📂 Data/
│   ├── cleaned/                                # cleaned data
│   ├── meta_reslts/                            # Stores intermediate analysis results, Example: feature importance, correlations
│   ├── raw/                                    # Raw, unprocessed data directly from APIs. This is the "source of truth"
│   │   ├── 1min/                               # High-frequency intraday data (~2 years), used for microstructure analysis & short-term signals
│   │   │   ├── NIFTY50_1min.csv
│   │   │   ├── BANKNIFTY_1min.csv
│   │   │   └── NIFTYNEXT50_1min.csv
│   │   ├── daily/                              # Long-term OHLCV data (2007–present), backbone for trend + volatility modeling
│   │   │   ├── NIFTY50_daily.csv
│   │   │   ├── BANKNIFTY_daily.csv
│   │   │   └── NIFTYNEXT50_daily.csv
│   │   ├── gpr/                                # Geopolitical Risk Index data, captures global + India-specific risk sentiment
│   │   ├── rss/                                # Real-time financial news from RSS feeds, short-term market-moving signals
│   │   ├── gdelt/                              # Global news dataset (2000–present), provides historical news coverage at scale
│   │   ├── alphavantage/                       # Pre-scored sentiment data, used as validation for FinBERT outputs
│   │   ├── yfinance/                           # Ticker-specific news data, provides company/index-focused sentiment
│   │   ├── wayback/                            # Archived news (2008–2015), fills historical gaps where APIs lack data
│   │   ├── sentiment/                          # FinBERT outputs (article-level sentiment), intermediate NLP results
│   │   ├── regime_events/                      # Structured dataset of major events: elections, budgets, crises, reforms
│   │   ├── fred/                               # Macroeconomic indicators (interest rates, FX, inflation), captures economic regime shifts
│   │   └── logs/                               # Data collection logs, ensures traceability and debugging capability
│   │       └── collection_log.csv
│   │
│   ├── processed/                              # Cleaned + feature-engineered datasets, ready for modeling
│
├── 📂 Documents/                        
│   ├── admin/                                  # A20, A21 and other approvals
│   ├── planning/                               # research calendar
│   ├── methodology/                            # model variables, documentation
│   └── references/                             # papers, literature
│
├── 📂 Outputs/
│   ├── plots/                                  # EDA + results graphs
│   ├── reports/                                # summaries / PDFs
│   ├── predictions/
│
├── 📂 Models/                                  # saved models (.pkl/.h5)
```
---

## 📊 Phase 01 — Data Pipeline (Completed ✅)

📄 Full documentation: 

### 🔹 What Was Built

A **production-grade data pipeline** that:

* Collects data from **8+ sources**
* Handles API limitations & missing data
* Standardizes everything into **one unified dataset**

---

### 🔹 Data Sources & Coverage

| Category | Source                        | Purpose                  |
| -------- | ----------------------------- | ------------------------ |
| Market   | Yahoo Finance + Zerodha       | Price + volume           |
| News     | GDELT, RSS, YFinance, Wayback | Sentiment signals        |
| Risk     | GPR Index                     | Geopolitical stress      |
| Macro    | FRED                          | Economic conditions      |
| Events   | ECI, RBI, Wikipedia           | Structural regime shifts |

---

### 🔹 Output

```bash
gpr_combined_monthly.csv
```

* 📅 2000 → 2026
* 📊 80+ features
* 🧠 Ready for ML/DL models

---

## 🧪 Phase 02 — EDA & Modeling (In Progress 🚧)

From your pipeline 

### What Happens Here:

Instead of blindly training models, this phase:

* Validates **statistical properties of markets**
* Confirms **volatility clustering**
* Identifies **regime behavior patterns**

---

### Planned Models

* Linear Regression → baseline
* Random Forest → feature interactions
* XGBoost → structured prediction
* LSTM → temporal dependencies
* Prophet → time-series baseline

---

## 📈 Expected Outcomes

* Identification of **high vs low volatility regimes**
* Improved predictions using **multi-source features**
* Evidence that **deep learning captures temporal structure better**

---

## 🧠 Key Innovations

### 1. Multi-Source Fusion

Instead of relying on a single dataset, the model learns from **independent signals**, improving robustness.

### 2. India-Specific Risk Modeling

GPR + macro + events are tailored to **Indian markets**, not generic global datasets.

### 3. NLP + Finance Integration

FinBERT converts raw news into **quantifiable sentiment signals**.

### 4. Bias-Free Event Encoding

Events are encoded structurally (not politically), ensuring **model neutrality**.

---

## ⚠️ Challenges & Limitations

* Pre-2015 sentiment uses proxy signals (GDELT tone)
* FinBERT trained on US financial data
* Some APIs have data limits (e.g., GDELT cap)
* Archived news (Wayback) may contain noise

---

## 🔮 Future Scope

* Real-time inference pipeline
* Trading signal generation
* Reinforcement learning strategies
* Deployment via Streamlit / API
* Explainable AI (SHAP, feature importance)

---

## 👤 Author

**Swagato Bag**
MTech (AI) – IIT Jodhpur
Data Scientist – RBL Bank

---

## 📜 License

Currently for academic use.
Can be extended to MIT / Apache 2.0.

---

## ⭐ If You Like This Project

Give it a ⭐ on GitHub — it helps visibility and motivates further development.

---

If you want next level upgrade, I can:

* 🎯 Add **GitHub banner image (very premium look)**
* 📊 Create **architecture diagram (visual flowchart)**
* 🧠 Write **research paper abstract + methodology section**
* 💼 Optimize this specifically for **resume + recruiter impact**

Just tell me 👍
