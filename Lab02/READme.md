# Lab 02 · NumPy for Numerical Computing

**Course:** CS-3105 Machine Learning Lab
**Lab Instructor:** Engr. Muhammad Awais
**Student:** Syeda Khadija Hassan · **Roll No:** 2024-SE-09
**Department:** Software Engineering, University of Azad Jammu & Kashmir, Muzaffarabad

## Objective

**CLO 5** (C-3 Apply, PLO 5 Modern Tool Usage): use Python programming and tools to perform data handling and basic operations.

This lab uses NumPy to create, reshape, slice, filter and aggregate arrays, and applies those skills to real Pakistani data (census, climate and inflation) and to a small image stored as an array.

## Files

| File | Description |
|------|-------------|
| `Lab02.ipynb` | Completed notebook (all 11 tasks, outputs included) |
| `README.md` | This file |

## What the notebook covers

| Task | Topic | Main NumPy tools |
|------|-------|------------------|
| 1 | Setup | `import numpy as np`, `np.__version__` |
| 2 | Class register: creating arrays | `zeros`, `ones`, `full`, `arange`, `eye`, `reshape` |
| 3 | Randomness and reproducibility | `random.seed`, `rand`, `randn`, `randint`, `unique(return_counts=True)` |
| 4 | Spacing and reshaping | `arange`, `linspace`, `reshape`, `sum(axis=1)`, `argmax` |
| 5 | Exam hall seating plan | indexing and slicing, `sum`, `std` |
| 6 | Census 2023 | broadcasting, boolean masks, compound growth rate, `argmax` |
| 7 | Climate of five cities | `mean(axis=0/1)`, `argmax(axis=1)`, masks, column slicing |
| 8 | Inflation FY2024 vs FY2025 | element-wise subtraction, masks, nested `np.where` |
| 9 | Grace marks | `clip`, masks, z-scores |
| 10 | An image is an array | slicing, `[:, ::-1]` flip, `255 - img`, cropping, `clip` |
| 11 | Reflection | written findings |

Tasks 6, 7 and 8 each include a short written interpretation of the results.

## Datasets (provided in the starter notebook, unchanged)

- **Census 2023:** Pakistan Bureau of Statistics, 7th Population and Housing Census (provinces, ICT, AJK, GB), with 2017 figures for growth rates.
- **Climate:** 1991-2020 climate normals (PMD / WMO) for Lahore, Karachi, Islamabad, Peshawar and Quetta (mean daily maximum temperature in °C and rainfall in mm).
- **Inflation:** Pakistan Economic Survey 2024-25, Chapter 7, Fig 7.1 (PBS CPI, year-on-year %).
- **Marks:** sample lab-section marks.

## Selected results

- **Census:** Punjab holds 51.58 % of the 247,541,947 people counted in 2023. Balochistan is the fastest-growing unit (3.19 % per year); AJK is the slowest (1.15 % per year) against a national rate of 2.52 %.
- **Climate:** Islamabad has the wettest monsoon (763.0 mm in Jul-Sep). Quetta receives only 6.0 % of its yearly rain in the monsoon. Peshawar has the highest monthly mean maximum (39.6 °C in June).
- **Inflation:** average CPI inflation fell from 26.22 % (FY2024) to 4.87 % (FY2025); the biggest monthly drop was in January (25.9 percentage points).
- **Grace marks:** the pass rate rises from 70 % to 90 % after 5 grace marks; two students pass only because of them.

## Approach and rules followed

- No Python loops or comprehensions: everything uses vectorised NumPy functions.
- Every output is labelled with its task ID and includes units, for example `T7e (months above 35 °C): ...`.
- Seeds are set (`2026` and `42`), so the random results are reproducible.
- The notebook was run with **Restart and run all** and completes without errors.

### Notes on specific choices

- **Task 3e** counts overlapping pairs, so a run of three sixes counts as two double-sixes. The expected value for a fair die (about 278) is printed next to the observed count.
- **Task 4a** builds the grid from integers (`np.arange(1, 101) / 100`) to avoid floating-point drift in `np.arange(0.01, 1.01, 0.01)`.
- **Task 7c:** Lahore's hottest month is a tie between May and June (both 38.9 °C); `argmax` returns the first, May.
- A small helper function, `table`, is defined in Task 1 to print aligned label/value lines without loops.

## How to run

**Requirements:** Python 3.9+ with `numpy` and `matplotlib` (the latter only for the optional plot in Task 10).

**Google Colab:** upload `Lab02.ipynb`, then choose Runtime → Restart and run all.

**Locally:**

```bash
pip install numpy matplotlib jupyter
jupyter notebook Lab02.ipynb
```

Then choose Kernel → Restart & Run All.

## Repository layout

```
ML-Lab-2024-SE-09/
└── Lab02/
    ├── Lab02.ipynb
    └── README.md
```
