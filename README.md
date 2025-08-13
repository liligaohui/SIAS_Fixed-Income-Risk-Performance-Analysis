# SIAS Fixed Income Risk Monitoring

## Overview

This repository contains a Python-based toolkit for monitoring and analyzing the **SIAS Fixed Income Portfolio** and its benchmark—without requiring direct Bloomberg access.
It enables the SIAS Risk Team to quantify active duration positioning, sector allocation differences, and scenario-driven performance impacts through a fully interactive stress-testing dashboard.

By simply pointing to the latest holdings files, you can reproduce key rate exposures, government/corporate allocation differences, and yield-curve shock impacts for both the SIAS portfolio and its benchmark (FTSE Canada Universe Bond Index, ticker: XBB).

## Features

* **Comprehensive Fixed Income Analytics:**

  * Macaulay & Modified Duration, convexity, active duration by maturity bucket, and active sector allocation (Gov/Province/Corporate).
* **Sector & Maturity Breakdown:**

  * Government vs Corporate exposure, duration-weight distribution by bucket, and bond-type mix.
* **Interactive Stress-Testing Dashboard:**

  * **Parallel Shifts:** Apply basis point shocks to the entire curve.
  * **Curve Steepener/Flattener:** Adjust short- and long-end independently.
  * **Key-Rate Shocks:** Bump selected maturity buckets (2y, 5y, 10y, 30y).
* **Automated Data Ingestion:**

  * Reads portfolio holdings from BNY Mellon exports and benchmark holdings from XBB constituent files.
* **Dynamic Visualization:**

  * Real-time updates in Jupyter/Colab with IPython widgets for parameter tuning.
* **Modular & Extensible:**

  * Easy to integrate new scenarios, benchmarks, or custom classifications.

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

   * File format: `.xlsx`
   * Source: BNY Mellon (latest file, retrieved via SFU email)

2. **Benchmark Holdings (XBB)**

   * File format: `.xlsx` or `.csv`
   * Source: FTSE Canada Universe Bond Index / iShares XBB constituent file

## Usage

1. **Clone or download** this repository.

2. **Open** the main analysis script (e.g., `fixed_income_risk_dashboard.py`) in Jupyter Notebook or Google Colab.

3. **Configure** file paths at the top of the script:

   ```python
   PORT_FILE = "SIAS_FI_Portfolio_dd-mm-yyyy.xlsx"
   BM_FILE   = "XBB_holdings_dd-mm-yyyy.csv"
   ```

4. **Run** the notebook or script:

   * Loads and aligns portfolio vs. benchmark holdings.
   * Displays portfolio & benchmark tables, active weights, maturity bucket durations, and sector allocation.
   * Launches interactive stress-testing dashboard.

5. **Export** results (optional):

   * CSV: `outputs/fixed_income_metrics_<date>.csv`
   * PNG charts: `outputs/<chart_name>_<date>.png`

## Verification & Quality Control

* **Cross-Check:** Compare active duration and sector allocation against Bloomberg or other validated risk systems.
* **Versioning:** Tag scripts and data files with a date stamp (e.g., `2025-08-08`) to ensure reproducibility.

## Notebooks & Colab

Interactive implementation available on Google Colab:
[Open in Colab »](https://colab.research.google.com/) *(link to your live notebook)*

## Contributing

Pull requests and issues are welcome for:

* New stress-testing scenarios
* Enhanced allocation visualizations
* Additional benchmark support

## Author & Contact

**Lili, Hui Gao**
Risk and Compliance Portfolio Manager\
Student Investment Advisory Service (SIAS) — SFU\
2024 Cohort\
✉️ [hga87@sfu.ca](mailto:hga87@sfu.ca)

*Last Updated: Aug 8, 2025*
