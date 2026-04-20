# 📊 Rolling PCA-Based Portfolio Optimization

## 🚀 Overview

This project explores **adaptive portfolio construction** using **Rolling Principal Component Analysis (PCA)** combined with clustering techniques. Unlike traditional methods that assume static relationships between assets, this approach dynamically updates market structure using recent data, improving risk-adjusted performance.

---

## 🎯 Problem Statement

Financial markets are **non-stationary**, meaning relationships between assets change over time.
Traditional PCA-based portfolio methods fail to capture these dynamics, leading to suboptimal diversification.

👉 This project addresses this by:

* Introducing **Rolling PCA**
* Combining it with **clustering**
* Evaluating its impact on portfolio performance

---

## 🧠 Methodology

### 1. Data

* Source: Yahoo Finance (`yfinance`)
* Assets: ~50 large-cap stocks across sectors
* Period:

  * Train: 2015–2020
  * Test: 2021–2023

---

### 2. Dimensionality Reduction

* **PCA (Static)** → computed once
* **Rolling PCA (Novelty ⭐)** → recomputed using moving window

---

### 3. Clustering

* K-Means
* Hierarchical Clustering (Ward linkage + correlation distance)

---

### 4. Portfolio Construction

Two-level **Inverse Volatility Weighting (IVW)**:

* Within-cluster allocation
* Across-cluster allocation

---

### 5. Evaluation Metrics

* Sharpe Ratio
* Annual Return
* Volatility
* Max Drawdown
* CVaR
* Win Rate
* Cluster Stability (ARI)

---

## 📈 Results Summary

| Strategy                       | Sharpe    | Return (%) | Max Drawdown (%) |
| ------------------------------ | --------- | ---------- | ---------------- |
| No PCA + KMeans                | 0.329     | 8.74       | -22.37           |
| Static PCA + KMeans            | 0.383     | 10.32      | -25.09           |
| Rolling PCA + KMeans           | 0.339     | 10.05      | -27.67           |
| **Rolling PCA + Hierarchical** | **0.474** | 10.72      | **-16.04**       |
| Equal Weight (1/N)             | 0.426     | 11.10      | -23.87           |

👉 Best model: **Rolling PCA + Hierarchical Clustering**

---

## 🔬 Key Insights

* Rolling PCA improves **adaptability to market changes**
* Hierarchical clustering produces **more stable clusters**
* Equal-weight portfolio has higher raw return but worse risk-adjusted performance
* Window size significantly impacts performance (optimal ≈ 30–120 days)

---

## 📊 Output Files

* `results_table.csv`
* `cumulative_returns.png`
* `drawdown.png`
* `metrics_bar.png`
* `cluster_stability.png`
* `window_sensitivity.png`
* `window_sensitivity.csv`

---

## ⚙️ Installation & Usage

### Install dependencies

```bash
pip install yfinance pandas numpy matplotlib seaborn scikit-learn scipy
```

### Run the project

```bash
jupyter notebook mlf_jackfruit.ipynb
```

---

## 🧪 Experimental Setup

* Rolling window: 60 days (default)
* Rebalancing: Monthly
* PCA variance threshold: 85%
* Clusters: 8

---

## 🌟 Novel Contribution

> This project introduces **Rolling PCA + Clustering** for portfolio optimization and evaluates:

* Cluster stability (ARI)
* Sensitivity to rolling window size

---

## 📚 References

* Jolliffe, I. T. (2002) — Principal Component Analysis
* DeMiguel et al. (2009) — Optimal vs Naive Diversification
* Mantegna (1999) — Hierarchical Structure in Financial Markets

---
Authors
Samarth Vinod Hosalli (PES1UG23AM261)
Siddarth Reddy (PES1UG23AM300)


## 📌 Notes

* This is an academic project for Machine Learning in Finance
* Results are for educational purposes only

---

