# Machine Learning Lab 03 · Pandas for Data Manipulation and Cleaning

**Course:** CS-3105 Machine Learning Lab  
**Lab Instructor:** Engr. Muhammad Awais  
**Student Name:** Syeda Khadija Hassan  
**Roll No:** 2024-SE-09  
**Department:** Department of Software Engineering, University of Azad Jammu & Kashmir (UAJK), Muzaffarabad  
**Term:** Semester 05 (Fall 2026)  
**CLO:** CLO 6 (C-4 Analyze, PLO 2 Problem Analysis) — *Analyze real-world datasets by applying data manipulation and visualization techniques.*

---

## 📋 Table of Contents
1. [Overview](#-overview)
2. [Dataset Details](#-dataset-details)
3. [Repository Structure](#-repository-structure)
4. [Tasks Summary](#-tasks-summary)
   - [Task 1: Load and First Look](#task-1--load-and-first-look)
   - [Task 2: Retrieve Data & Filtering](#task-2--retrieve-data--filtering)
   - [Task 3: Clean the Data (Six Problem Types)](#task-3--clean-the-data-six-problem-types)
   - [Task 4: Analysis & Written Interpretations](#task-4--analysis--written-interpretations)
   - [Task 5: Save Cleaned Dataset](#task-5--save-cleaned-dataset)
   - [Task 6: Reflection](#task-6--reflection)
   - [Bonus Tasks](#bonus-tasks)
5. [Setup and Execution](#-setup-and-execution)
6. [Submission Checklist](#-submission-checklist)

---

## 🔍 Overview
This repository contains the complete implementation and analytical report for **Lab 03 (Pandas for Data Manipulation and Cleaning)**. The lab focuses on manipulating, diagnosing, cleaning, and analyzing a real-world secondary automotive marketplace dataset from Pakistan, resolving six fundamental data hygiene problems without employing procedural row loops.

---

## 📊 Dataset Details
- **File:** `pakistan_used_cars.csv`
- **Source:** OLX Pakistan (Open Data Pakistan, *Pakistan Used Cars*, 2021)
- **Raw Dimensions:** 24,973 listings × 9 attributes
- **Attributes:**
  - `Brand` *(categorical)*
  - `Condition` *(categorical: Used / New)*
  - `Fuel` *(categorical: Petrol, Diesel, CNG, Hybrid, LPG)*
  - `KMs Driven` *(numerical / float)*
  - `Model` *(categorical)*
  - `Price` *(raw text object containing currency markers and commas)*
  - `Registered City` *(categorical)*
  - `Transaction Type` *(categorical: Cash, Installment/Leasing)*
  - `Year` *(numerical / float)*

---

## 📂 Repository Structure
```text
ML-Lab-2024-SE-09/
├── README.md                           # Main repository documentation
└── Lab03/
    ├── README.md                       # Lab documentation
    ├── Lab03.ipynb                     # Executed Jupyter Notebook with outputs
    ├── pakistan_used_cars.csv          # Raw dataset
    └── pakistan_used_cars_clean.csv    # Cleaned dataset exported in Task 5
```

---

## 🛠 Tasks Summary

### Task 1 · Load and First Look
- Loaded `pakistan_used_cars.csv` into a Pandas DataFrame; inspected shape `(24973, 9)` and previewed first 5 rows.
- Examined column names and data types.
- Identified that `Price` was incorrectly typed as `object` (string) due to embedded characters like `"Rs"` and commas (e.g., `"Rs 1,430,000"`).

### Task 2 · Retrieve Data & Filtering
- Retrieved specific columns and subsets using column indexing, `.iloc`, and `.loc`.
- Applied boolean masks to retrieve subsets:
  - Vehicles registered in Islamabad: **779 ads**
  - Honda hybrid cars: **28 ads**
  - Vehicles from 2018 or newer sorted descending by year.
- **Task 2(h) Analysis:** Documented why `df[df["Price"] > 1_000_000]` raises a `TypeError` (string vs integer comparison in Python before cleaning).

### Task 3 · Clean the Data (Six Problem Types)
1. **Missing Values:**
   - Identified missing counts per column.
   - Dropped rows with missing `Brand` or `Model`.
   - Filled missing `Registered City`, `Fuel`, and `Transaction Type` with `"Unknown"`. Left `Year` and `KMs Driven` as `NaN`.
2. **Formatting:**
   - Standardized `Registered City` using `.str.strip().str.title()`.
   - Stripped currency symbol `"Rs"` and commas from `Price`.
3. **Data Types:**
   - Converted `Price` to `int64` and `Year` to nullable `Int64`.
4. **Inconsistent Categories:**
   - Corrected typos: `"Sukkar"` $	o$ `"Sukkur"` and `"Corrolla Altis"` $	o$ `"Corolla Altis"`.
   - Verified that unique city count reduced from 62 to 61.
5. **Duplicates:**
   - Identified and removed **2,028** exact duplicate listings, reducing row count to 20,497.
6. **Invalid Values & Outliers:**
   - Set impossible `KMs Driven` (< 100, > 1,000,000, or placeholders 12345 / 123456) to `NaN`.
   - Dropped fake prices (`12345678`, `87654321`) and unrealistic budget vehicles (`Suzuki`/`Daihatsu` > 5M).
- **Self-Check:** Verified and asserted the required clean shape of **`(20484, 9)`**.

### Task 4 · Analysis & Written Interpretations
- **Derived Features:** Created `Price_lakh` (`Price / 100,000`) and `Age` (`2020 - Year`).
- **Distributions:**
  - Most common brands: Suzuki (8,621), Toyota (4,535), Honda (3,025), Daihatsu (2,231), Nissan (694).
  - Top cities (all): Karachi (15,461), Unknown (2,040), Lahore (1,601), Islamabad (777), Rawalpindi (119).
  - Top cities (excluding `"Unknown"`): Karachi (15,461), Lahore (1,601), Islamabad (777), Rawalpindi (119), Multan (88).
- **Powertrain Price Comparison:**
  - Hybrid: 16.28 lakh (highest median)
  - Diesel: 13.00 lakh
  - Petrol: 8.75 lakh
  - CNG: 3.85 lakh
  - LPG: 1.58 lakh (lowest median)
- **4(f) Corolla GLI Depreciation Analysis:**
  - Evaluated median prices across model years 2010 (12.25 lakh) to 2018 (23.20 lakh).
  - Total median difference: **10.95 lakh rupees**, translating to an average value difference of **~1.37 lakh rupees per year**.
  - Clarified that these represent cross-sectional comparisons across ads rather than a longitudinal tracking of a single vehicle.
- **4(g) Outlier Analysis & Model Medians:**
  - Computed model medians via code:
    - Land Cruiser: 24.0 lakh
    - Prius: 18.2 lakh
    - Surf: 19.9 lakh
  - Demonstrated that three of the top five most expensive ads reflect data entry typos (accidental extra zeros):
    - *2015 Prius at 357.5 lakh:* ~14× the ~25 lakh median for 2014–2016 Prius ads.
    - *2005 Land Cruiser at 520.0 lakh:* ~12× the ~44 lakh median for 2003–2007 Land Cruiser ads (13 ads).
    - *2007 Surf at 410.0 lakh:* ~10× the ~41.5 lakh median for 2005–2009 Surf ads (5 ads).
- **4(h) Cash vs Installment Interpretation:**
  - Over 95% of ads are Cash (median 6.90 lakh) versus Installment (median 3.00 lakh).
  - Lower median price for installments likely indicates that classified listings advertise only the upfront down payment / advance token rather than total financed cost, or that financing is more commonly offered on budget models.

### Task 5 · Save Cleaned Dataset
- Exported clean DataFrame to [`pakistan_used_cars_clean.csv`](Lab03/pakistan_used_cars_clean.csv) with final shape `(20484, 11)` (including `Price_lakh` and `Age`).

### Task 6 · Reflection
> Ignoring invalid values and extreme outliers (such as placeholder prices like Rs 87,654,321 or miskeyed figures) would have produced the most misleading answers by heavily skewing mean prices and summary statistics. In the Pakistani used-car market, Japanese economy manufacturers heavily dominate supply, with Suzuki alone accounting for over 42% of all advertisements. Furthermore, hybrid vehicles command the highest median price across fuel types at 16.28 lakh rupees, whereas CNG and LPG vehicles sit at the lowest median prices under 4 lakh rupees.

### Bonus Tasks
1. **Highest Median Price Brand (≥ 50 ads):** Mercedes-Benz (15.75 lakh median), followed by Toyota (13.20 lakh).
2. **Relative Outlier Detection:** Flagged 97 listings exceeding 5× their respective model's median price.
3. **Vintage "New" Cars:** Identified 2,035 listings flagged with condition "New" despite being manufactured prior to 2015.

---

## 🚀 Setup and Execution

### Requirements
- Python 3.9+
- `pandas`
- `numpy`
- `jupyter` / `nbconvert`

### Instructions
1. Clone or extract this repository into your environment:
   ```bash
   git clone https://github.com/<your-username>/ML-Lab-2024-SE-09.git
   cd ML-Lab-2024-SE-09/Lab03
   ```
2. Launch Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook Lab03.ipynb
   ```
3. To execute all cells programmatically from the terminal:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace Lab03.ipynb
   ```

---

## ✅ Submission Checklist
- [x] Subfolder path matches specification: `ML-Lab-2024-SE-09/Lab03/Lab03.ipynb`
- [x] Student Name (**Syeda Khadija Hassan**) and Roll Number (**2024-SE-09**) filled in
- [x] All outputs labeled with `print("T...:", ...)`
- [x] Self-check assert passed: `df.shape == (20484, 9)`
- [x] Cleaned dataset `pakistan_used_cars_clean.csv` included in the same folder
- [x] Analytical interpretations (Tasks 2h, 4f, 4g, 4h, and 6) completed and checked
- [x] Notebook executed cleanly with all cell outputs saved

