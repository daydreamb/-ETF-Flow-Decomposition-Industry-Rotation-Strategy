## 📈 Factor Construction & IC Decomposition

This project constructs a comprehensive **ETF flow-based factor system** and evaluates its predictive power using **cross-sectional Information Coefficient (IC)**.

---

### 🧩 Factor Construction

We construct **52 flow-based factors** for each category of investors:

- Institutional flows  
- Retail flows  
- Mixed (ambiguous) flows  
- Industry-level aggregated flows  
- Broad-based ETF flows  

In addition, we construct **52 differential (spread) factors**, capturing relative positioning between different investor types.

---

### 🔍 Factor Types

The factors include:

- Absolute fund flows  
- Normalized flow signals  
- Flow momentum  
- Relative flow strength  
- Cross-investor differential signals  

These factors are designed to capture different dimensions of capital flow dynamics.

---

### 🧠 Investor Decomposition

ETF flows are decomposed into:

- **Institutional investors** (mutual funds, insurance, brokers, etc.)  
- **Retail investors**  
- **Mixed category** (similar institutional/retail proportions)  

This decomposition is achieved through:

- Investor composition data  
- ETF–feeder linkage (look-through ownership)  

---

### 📊 IC Computation

For each factor, predictive power is evaluated using **cross-sectional Information Coefficient (IC)**:

- IC is calculated as the correlation between:
  - factor values at time *t*  
  - subsequent returns at time *t+1*  

- IC is computed on a **weekly basis (IC weeks)**  
- Results are stored as time-series and summary statistics  

---

### 📁 Output Structure

The results are organized into:

- **Factor values** (52 factors per category)  
- **Differential factors** (52 spread signals)  
- **IC time series** (`ICweeks.xlsx`)  
- **Differential IC time series**  

These outputs are available for:

- Institutional factors  
- Retail factors  
- Mixed factors  
- Industry-level factors  
- Broad-based ETF factors  

---

### 📈 Key Observations

- Flow-based factors exhibit **consistent predictive signals** in IC  
- Differential factors often show **stronger signal strength**  
- Institutional flow factors tend to have **more stable IC performance**  
- Signal strength varies across industries and ETF universes  

---

### ⚠️ Notes

- This framework focuses on **signal evaluation**, not portfolio backtesting  
- IC is used as the primary metric for factor effectiveness  
- Results are sensitive to:
  - ETF universe definition  
  - investor classification  
  - data frequency  

---

### 🔄 Broad-Based ETF Extension

The same factor construction and IC evaluation framework is applied to:

- **Broad-Based ETF Universe**

This allows comparison between:

- Industry rotation signals  
- Broad market allocation signals  

and highlights structural differences in flow dynamics across ETF types.
