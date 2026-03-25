

# 📊 ETF Flow Decomposition & Industry Rotation Strategy

## 🔍 Overview

This project builds a **data-driven ETF flow decomposition framework** to analyze how different investor types drive market dynamics, and further evaluates the predictive power of ETF flows on **industry-level returns**.

Unlike traditional approaches that treat ETF flows as a single aggregate signal, this project decomposes flows into:

* Institutional flows
* Retail flows
* Mixed (ambiguous) flows

and studies their **cross-sectional predictive ability (IC, Information Coefficient)** on future returns.

---

## ⚙️ Key Contributions

* Constructed a **daily ETF flow dataset** using share changes
* Developed a **look-through ownership (股权穿透, look-through ownership)** methodology using feeder funds
* Decomposed flows into **investor-type-specific signals**
* Built **industry-level return series** using market-cap weighting
* Evaluated predictive power using **Information Coefficient (IC)**
* Extended analysis to **Top 10 institutional holders profiling**

---

## 🗂️ Data Description

Data is sourced from internal ETF datasets and consists of:

### Core Data

* **ETF.csv**
  Daily ETF share and fund flow data
  → Used to compute ETF-level flow changes

* **Composition.csv**
  Investor composition (institution vs retail)
  → Used for ownership classification

* **ETF_link.csv**
  ETF feeder fund holdings
  → Used for **look-through ownership adjustment**

* **Top10.csv**
  Top 10 holders
  → Used for institutional profiling

* **Institution Labels.csv**
  Pre-classified institution types (e.g., broker, insurance)
  → Used for investor segmentation

* **Initial Fund Size.csv**
  Used for scaling and normalization

---

## 🧠 Methodology

### 1. Flow Construction

ETF flow is defined as:

![image](https://github.com/user-attachments/assets/372b7ead-56f4-442c-93ac-5d130fcdc266)

This serves as the core explanatory variable (X).

---

### 2. Industry Return Construction

* ETFs are grouped into ~31 industries
* Industry returns are computed using **market-cap weighted returns**

![image](https://github.com/user-attachments/assets/6c5d0e84-079e-4d4f-857e-439ecd2ea1bc)


This serves as the dependent variable (Y).

---

### 3. Flow Decomposition (Core Innovation)

Using investor composition + look-through ownership:

* **Institutional Flow**
* **Retail Flow**
* **Ambiguous Flow (混合资金)**

Key step:

➡️ Adjust ETF ownership using feeder funds
➡️ Estimate *true institutional holding ratio*

---

### 4. Predictive Power (IC Analysis)

We compute **Information Coefficient (IC)**:

[
IC = corr(Flow_t, R_{t+1})
]

Applied to:

* Aggregate flows
* Institutional flows
* Retail flows

---

### 5. Institutional Profiling

Using Top 10 holders + labeled data:

* Public funds (公募基金)
* State-owned capital (国资)
* Brokers / Insurance

Used to analyze:

* Which institutions drive flows
* Structural behavior differences

---

### 6. Time Segmentation

Analysis is extended across:

* ETF age (new vs mature funds)
* Different market periods

---

## 📈 Strategy Insight

### Key Finding

👉 **ETF flows contain predictive information for industry returns**

👉 **Institutional flows have stronger predictive power than retail flows**

---

### Why?

* Institutional investors are more **information-driven (information advantage)**
* Retail flows are often **noise or sentiment-driven**
* Flow decomposition improves signal-to-noise ratio

---

## 🧪 Extensions

This framework can be extended to:

* Factor construction (Flow-based factors)
* Timing strategies (Flow timing)
* Cross-asset allocation
* Smart beta signals

---

## 💻 Code Structure

```
├── 行业ETF数据处理计算.ipynb     # Industry ETF flow analysis
├── 宽基ETF数据处理与计算.ipynb   # Broad ETF analysis
├── data/
│   ├── ETF.csv
│   ├── Composition.csv
│   ├── ETF_link.csv
│   ├── Top10.csv
│   └── ...
├── output/
│   ├── IC_results.xlsx
│   ├── flow_decomposition.xlsx
```

---

## 🚀 Usage

1. Update raw data (adjust `end_date`)
2. Run notebook:

   * Industry ETF analysis
   * Broad ETF analysis
3. Export results to Excel

---

## ⚠️ Notes

* No machine learning models are used
* Focus is on **data engineering + financial intuition**
* Framework is modular and extendable

---

## 📌 Future Improvements

* Add **factor backtesting (long-short portfolio)**
* Introduce **machine learning models (Lasso, PCA)**
* Improve classification of ambiguous flows
* Incorporate **high-frequency data**

---

## 🧾 Summary

This project provides a **clean and scalable framework** for:

* ETF flow decomposition
* Investor behavior analysis
* Industry return prediction

It demonstrates how **data processing + financial logic** can generate **actionable quantitative signals**.


你下一步把图表给我，我可以帮你把 README 直接升级成 **顶级 GitHub 项目水平（可以面试讲的那种）**
