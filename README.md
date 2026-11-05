# Machine Learning Lab

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Arrays-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
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
| [Lab 01](Lab_01) | Python fundamentals: strings, lists, dictionaries, functions, conditionals | Done |
| [Lab 02](Lab_02) | NumPy for numerical computing: array creation, reshaping, slicing, masking, broadcasting and `axis`, seeded random numbers, and analysis of real census, climate and inflation data | Done |
| [Lab 03](Lab03) | Pandas for data manipulation and cleaning: indexing, filtering, handling missing/invalid values, text standardization, deduplication, type casting, and exploratory analysis of real-world used-car marketplace data | Done |

> New labs are added to this table as they are completed.

## Repository Structure

```text
ML-Lab-2024-SE-09/
├── README.md
├── Lab_01/
│   ├── README.md
│   └── Lab01.ipynb
├── Lab_02/
│   ├── README.md
│   └── Lab02.ipynb
└── Lab03/
    ├── README.md
    ├── Lab03.ipynb
    ├── pakistan_used_cars.csv
    └── pakistan_used_cars_clean.csv
```

Every new lab follows the same pattern: a lab folder with its own `README.md`, notebook (`LabXX.ipynb`), and any required datasets.

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/ML-Lab-2024-SE-09.git
   cd ML-Lab-2024-SE-09
   ```
2. Install Jupyter and the libraries used so far:
   ```bash
   pip install notebook numpy pandas matplotlib
   ```
3. Open any lab notebook:
   ```bash
   jupyter notebook Lab03/Lab03.ipynb
   ```

Lab 01 needs only Python. Lab 02 needs NumPy, plus matplotlib for one optional plot. Lab 03 needs Pandas and NumPy. Later labs may need more libraries (for example scikit-learn); each lab's README lists what it needs.

## Tools Used

- Python 3
- Jupyter Notebook
- NumPy (Lab 02 onwards)
- Pandas (Lab 03 onwards)
- Matplotlib (Lab 02, optional plot)
- Git and GitHub

## Author

**Syeda Khadija Hassan**, Roll No 2024-SE-09  
Department of Software Engineering, University of Azad Jammu & Kashmir, Muzaffarabad
