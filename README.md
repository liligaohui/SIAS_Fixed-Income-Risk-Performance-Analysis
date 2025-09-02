# SIAS Fixed Income Risk & Performance Monitoring

## Overview

This repository provides a Python-based toolkit for monitoring and analyzing the **SIAS Fixed Income Portfolio** and its benchmark—without requiring direct Bloomberg access.

It enables the SIAS Risk Team to quantify active duration positioning, sector allocation differences, and scenario-driven performance impacts through a fully interactive stress-testing dashboard.

By pointing to the latest holdings files, you can reproduce key rate exposures, government/corporate allocation differences, and yield-curve shock impacts for both the SIAS portfolio and its benchmark: **FTSE Canada Universe Bond Index (iShares XBB)** ([Web Page](https://www.blackrock.com/ca/investors/en/products/239493/ishares-canadian-universe-bond-index-etf)).


## Features

* **Comprehensive Fixed Income Analytics**

  * Macaulay & Modified Duration, convexity, active duration by maturity bucket, and active sector allocation (Federal/Provincial/Corporate).

* **Sector & Maturity Breakdown**

  * Federal vs. Corporate exposure, duration-weight distribution by bucket, and bond-type mix.

* **Interactive Stress-Testing Dashboard**

  * **Parallel Shifts:** Apply basis-point shocks across the curve.
  * **Curve Steepener/Flattener:** Adjust short- and long-end independently.
  * **Key-Rate Shocks:** Bump selected maturity buckets (2y, 5y, 10y, 30y).

* **Automated Data Ingestion**

  * Reads portfolio holdings from BNY Mellon exports and benchmark holdings from XBB constituent files.

* **Dynamic Visualization**

  * Real-time updates in Jupyter/Colab with IPython widgets for parameter tuning.

* **Modular & Extensible**

  * Easily extend with new scenarios, benchmarks, or custom classifications.


## Prerequisites

1. **Python 3.8+**
2. Core libraries:

   * `pandas`
   * `numpy`
   * `matplotlib`
   * `requests`
   * `ipywidgets`
3. Recommended environment:

   * Jupyter Notebook / Google Colab

## Data Inputs

1. **SIAS Fixed Income Portfolio Holdings**

   * Format: `.xlsx`
   * Source: BNY Mellon (retrieved via SFU email)

2. **Benchmark Holdings (XBB)**

   * Format: `.xlsx` or `.csv`
   * Source: FTSE Canada Universe Bond Index / iShares XBB constituent file

### Data Access
The dataset used in this project is not publicly available in this repository.  
A copy is hosted on Google Drive. To obtain access:

1. Visit the [Dataset Request Link](https://drive.google.com/drive/folders/1quHwjtSB1DkfSWaD2bA1_XT-s8HOqZkx?usp=sharing).  
2. Submit an access request using your Google account.  
3. Access will be granted on a case-by-case basis for academic and research purposes.  

Note: Without this dataset, the analysis code will run but produce empty outputs or require substitution with your own data.

## Usage

1. **Clone or download** this repository.

2. **Open** the main analysis script (e.g., `fixed_income_risk_dashboard.py`) in Jupyter Notebook or Google Colab.

3. **Configure** file paths at the top of the script:

   ```python
   PORT_FILE = "yyyymmdd SIAS_FI_Portfolio_mm dd yyyy.xlsx"
   BM_FILE   = "XBB_holdings_m dd yyyy.csv"
   ```

4. **Run** the notebook or script to:

   * Load and align portfolio vs. benchmark holdings.
   * Display portfolio & benchmark tables, active weights, maturity bucket durations, and sector allocations.
   * Launch the interactive stress-testing dashboard.


## Verification & Quality Control

* **Cross-Check:** Validate active duration and sector allocation against Bloomberg or other risk systems.
* **Versioning:** Tag scripts and data files with a date stamp (e.g., `2025-08-08`) to ensure reproducibility.

### Assumptions

1. No look-through applied to underlying funds.
2. All figures are in CAD.
3. Scenario analysis assumes portfolio weights remain constant during the simulation period.
4. Convexity effects are excluded from scenario analysis.


## Notebooks & Colab

Interactive implementation available on Google Colab:
[**Open in Colab »**](https://colab.research.google.com/drive/1wOz3mYphzrIWeIp3SdGKsVa1yM6HPdO9?usp=sharing)



## Author & Contact

**Lili Hui Gao**
Risk & Compliance Portfolio Manager
Student Investment Advisory Service (SIAS) – SFU
2024 Cohort
✉️ [hga87@sfu.ca](mailto:hga87@sfu.ca)

*Last updated: Sep 1, 2025*

Do you want me to also make a shorter version of this (like an executive summary style) for GitHub’s main page, and keep the detailed one in a `docs/` folder?
