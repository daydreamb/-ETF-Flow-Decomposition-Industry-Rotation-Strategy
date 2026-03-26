

# 📊 Data & Universe Description

## 📁 Core Datasets

```markdown
### ETF Flow Data

- **ETF.csv**  
  Daily ETF share and capital flow data.  
  Used to compute ETF daily fund flows.

- **investor_composition.csv**  
  Provides the breakdown of institutional vs retail ownership for each ETF.  
  Used together with ETF linkage data for look-through ownership analysis.

- **etf_linkage.csv**  
  Contains the holding relationships between ETFs and their feeder funds.  
  Used for look-through ownership adjustment.

- **top10_holders.csv**  
  Top 10 holder information for each ETF.  
  Used for institutional profiling (e.g., mutual funds, state-owned capital).

- **institution_labels.csv**  
  Pre-classified institutional categories from the Juyuan database（Gildata聚源）.  
  Validated in industry analysis and used for ongoing updates (e.g., brokers, insurance).

- **initial_fund_size.csv**  
  Used to compute initial issuance size of ETFs.  
  Applied in later-stage analysis.

- **master_output.xlsx**  
  Output file generated after each run, containing updated results and intermediate calculations.
```

---

## 🧠 ETF Universe Construction

```markdown
### Industry ETF Universe Construction

Defines the universe of sector ETFs used for rotation analysis.

- Coverage: up to January 2025  
- ~31 industry classifications based on a refined taxonomy  
- Selected from ~400+ ETFs to ensure broad market coverage  

Sheets:

- **ETF**  
  Core industry ETFs (excluding feeder funds), used in total flow analysis  
  Also used for ETF overlap analysis via security codes  

- **All Industry ETFs**  
  Full list of industry ETFs used to compute total market coverage  
  Enables calculation of selected ETF market cap proportion  

- **ETF–Feeder Mapping**  
  Contains both ETFs and their feeder funds  
  Used for look-through ownership adjustment  
```

---

```markdown
### Broad-Based ETF Universe

Defines the universe of broad market ETFs.

- Coverage: up to January 2025  

Sheets:

- **Broad Market ETFs**  
  Used in total flow analysis  

- **ETF–Feeder Mapping**  
  Includes broad ETFs and corresponding feeder funds  
  Used for ownership decomposition into:
  - Institutional  
  - Retail  
  - Mixed (ambiguous)  
```

---

## 📥 Data Source & Update

```markdown
- Data sourced from internal database (堡垒机)  
- Coverage: up to January 2025  
- Total observations: ~1,121 ETF–feeder link pairs  

- Wind and Bloomberg are required for:
  - ETF–feeder mapping  
  - Supplementary data validation  

### Update Method

- Full refresh: update `end_date` and re-download complete dataset  
- Incremental update: append new data and merge with historical dataset manually  
```

---

## 🔒 Code Availability

```markdown
Part of the data pipeline and production-level code was developed within an internal environment during my internship at a financial institution.

Due to confidentiality and compliance requirements, these components cannot be publicly disclosed.

This repository provides a reconstructed and simplified version of the workflow, focusing on the research logic, including:

- ETF flow construction  
- Investor decomposition (look-through ownership)  
- Factor construction and IC analysis  

The goal is to demonstrate the underlying quantitative methodology while respecting data and code privacy constraints.


