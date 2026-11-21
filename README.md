# Machine Learning Lab

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Arrays-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Machine%20Learning-F7931E?logo=scikitlearn&logoColor=white)
![Course](https://img.shields.io/badge/Course-CS--3105-blue)

Lab work for the **Machine Learning** course (CS-3105), Semester 5.

| | |
|:--|:--|
| **Name** | Syeda Khadija Hassan |
| **Roll No** | 2024-SE-09 |
| **Batch** | BS Software Engineering, 2024-28 |
| **University** | University of Azad Jammu & Kashmir, Muzaffarabad |

---

## About This Repository

This repository holds my lab submissions for the Machine Learning course. Each lab lives in its own folder with a Jupyter notebook, associated datasets, and a README that explains what the lab covers and how to run it.

## Labs

| Lab | Topic | Status |
|:--:|:--|:--:|
| [Lab 01](Lab01) | Python fundamentals: strings, lists, dictionaries, functions, conditionals | Done |
| [Lab 02](Lab02) | NumPy for numerical computing: array creation, reshaping, slicing, masking, broadcasting and `axis`, seeded random numbers, and analysis of real census, climate and inflation data | Done |
| [Lab 03](Lab03) | Pandas for data manipulation and cleaning: indexing, filtering, handling missing/invalid values, text standardization, deduplication, type casting, and exploratory analysis of real-world used-car marketplace data | Done |
| [Lab 05](Lab05) | Simple linear regression for used-car price prediction using NumPy and scikit-learn, with train/test evaluation, residual analysis, and visualizations | Done |

> New labs are added to this table as they are completed.

## Repository Structure

```text
ML-Lab-2024SE09/
├── README.md
├── Lab01/
│   ├── README.md
│   └── Lab01.ipynb.ipynb
├── Lab02/
│   ├── README.md
│   └── Lab02.ipynb
├── Lab03/
│   ├── README.md
│   ├── Lab03.ipynb
│   ├── pakistan_used_cars.csv
│   └── pakistan_used_cars_clean.csv
└── Lab05/
    ├── READme.md
    ├── Lab05.ipynb
    ├── pakistan_used_cars_clean.csv
    └── images/
        ├── fitted_line.png
        ├── residual_plot.png
        └── scatter_age_vs_price.png
```

Every new lab follows the same pattern: a lab folder with its own `README.md`, notebook (`LabXX.ipynb`), and any required datasets.

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/hassankhadija06/ML-Lab-2024SE09.git
   cd ML-Lab-2024SE09
   ```
2. Install Jupyter and the libraries used so far:
   ```bash
   pip install notebook numpy pandas matplotlib scikit-learn
   ```
3. Open any lab notebook:
   ```bash
   jupyter notebook Lab05/Lab05.ipynb
   ```

Lab 01 needs only Python. Lab 02 needs NumPy and Matplotlib for optional visualization. Lab 03 needs Pandas and NumPy. Lab 05 also needs scikit-learn for `LinearRegression`, train/test splitting, and evaluation metrics.

## Tools Used

- Python 3
- Jupyter Notebook
- NumPy (Lab 02 onwards)
- Pandas (Lab 03 onwards)
- Matplotlib (Lab 02, optional plot)
- scikit-learn (Lab 05)
- Git and GitHub

## Author

**Syeda Khadija Hassan**, Roll No 2024-SE-09  
Department of Software Engineering, University of Azad Jammu & Kashmir, Muzaffarabad
