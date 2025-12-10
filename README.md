 
# 📦 Delhivery Delivery Time Analysis & SLA Optimization

## 📌 Project Overview

This project analyzes delivery performance data from **Delhivery** to understand delays, evaluate route-based time estimates (OSRM), and identify operational and data-driven improvements to optimize **SLA performance**.

The analysis focuses on:

* Comparing **actual delivery time vs estimated (OSRM) time**
* Identifying **systematic underestimation** in routing models
* Detecting **outliers and extreme delays**
* Understanding **destination-level bottlenecks**
* Providing **actionable business recommendations**

---

## 🎯 Business Objective

To determine whether delivery delays are random or systemic, identify where and why SLAs are breached, and recommend targeted interventions that improve delivery reliability without increasing overall operational cost.

---

## 🗂️ Dataset Description

The dataset contains shipment- and trip-level information including:

* Order creation and trip timestamps
* Start and end times of delivery legs
* Actual delivery time
* OSRM (route-based) estimated time
* Source and destination details

**Rows:** ~145,000
**Columns:** Trip metadata, timestamps, distances, estimated and actual time metrics

---

## 🔍 Analysis Performed

### 1. Data Cleaning & Exploration

* Inspected data structure, missing values, and data types
* Parsed datetime fields to enable time-based analysis
* Created derived features for delivery duration

### 2. Feature Engineering

* Created delivery duration metric:
  **`od_od_duration_mins` = od_end_time − od_start_time**
* Enabled downstream SLA and efficiency analysis

### 3. Hypothesis Testing (Actual vs OSRM)

* Performed **paired t-test** between actual delivery time and OSRM estimates
* Found **statistically significant difference (p < 0.05)**
* Observed consistent underestimation by OSRM

### 4. Distribution Analysis

* Delivery durations show **right-skewed distribution**
* Presence of long-tail delays affecting SLA performance
* Mean delivery time higher than median

### 5. Outlier Detection

* Used **IQR method** to flag extreme delays
* Identified **373 high-impact outlier deliveries**
* These represent exceptional operational failures or data issues

### 6. Destination-Level Analysis

* Grouped delivery durations by destination
* Identified locations with consistently higher delays
* Confirmed delays are **location-specific**, not network-wide

---

## 📊 Key Insights

* OSRM estimates **systematically underestimate** real delivery time
* SLA breaches are driven by:

  * Destination-specific constraints
  * A small fraction of extreme delay cases
* Averages hide risk; **percentile metrics** provide better SLA visibility

---

## ✅ Business Recommendations

### Operational

* Recalibrate OSRM estimates using historical actuals
* Add **destination-level buffers** to SLA commitments
* Focus operational improvements on top slow destinations
* Conduct root-cause analysis on outlier deliveries

 
## 🛠️ Tools & Technologies

* **Python**
* **Pandas, NumPy**
* **Matplotlib**
* **SciPy (Hypothesis Testing)**
* **Jupyter Notebook**

---
 
## 🚀 How to Run

1. Clone the repository
2. Install required libraries
3. Open `delhivery_analysis_final.ipynb`
4. Run all cells top-to-bottom

---

## 💡 Why This Project Matters

This case study demonstrates how data analysis can:

* Move beyond dashboards into **decision-making**
* Identify root causes instead of symptoms
* Translate statistical results into **business action**

---

## 📬 Contact

If you'd like to discuss this project or similar analytical work, feel free to connect.

 
