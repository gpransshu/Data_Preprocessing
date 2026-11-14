# Data Preprocessing

A hands-on collection of Jupyter notebooks demonstrating fundamental pandas data preprocessing and feature engineering techniques (course work in *Data Preprocessing and Feature Engineering*).

## Overview

The notebooks cover, in sequence:

1. **`DataFrame-Copy1.ipynb`** — Core pandas operations on small dataframes built from dicts:
   - Inspecting data: `head()`, `columns`, `info()`, `isnull()`
   - Accessing rows and columns: single/multiple column selection, `loc[]` and `iloc[]`
   - Conditional selection: boolean masks, combined conditions (`&`)
   - Adding and deleting columns (including `drop(..., axis=1, inplace=True)`)
   - Handling missing values: `isnull()` and `dropna()` (with `thresh` and `axis`)

2. **`encoding.ipynb`** — Basic value encoding:
   - Remapping category labels with `DataFrame.replace()`
   - Checking distributions with `value_counts()`
   - Converting a column to `category` dtype with `astype('category')`

3. **`House Dataset/DPFEassignment.ipynb`** — Preprocessing an Excel housing dataset (`pransshu.xlsx`):
   - Reading Excel with `pd.read_excel()`
   - Dropping missing values (`dropna()`, `dropna(thresh=2)`)
   - Filling missing values with **mean**, **median**, and **mode**
   - Value replacement and label remapping with `replace()`
   - One-hot encoding with `pd.get_dummies()` (including `prefix`, `prefix_sep`, `dummy_na`)
   - Ordinal encoding with `sklearn.preprocessing.OrdinalEncoder`

4. **`merge join/merge join class.ipynb`** — Combining dataframes:
   - Concatenation with `pd.concat()`
   - Merging with `pd.merge()` using `inner`, `left`, and `right` joins on shared keys
   - Joining with `DataFrame.join()` on a stress dataset read from Excel

## Tech Stack

- Python
- Jupyter Notebook
- [pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)
- [scikit-learn](https://scikit-learn.org/) (used for `OrdinalEncoder` in the house dataset assignment)

Data is read from Excel (`.xlsx`) and CSV files. No environment/requirements file is provided; the notebooks import `pandas`, `numpy`, and (in one notebook) `sklearn`.

## Project Structure

```
.
├── DataFrame-Copy1.ipynb            # Core pandas operations: access, selection, columns, missing values
├── encoding.ipynb                   # Value replacement and categorical encoding
├── House Dataset/
│   ├── DPFEassignment.ipynb         # Missing-value imputation and encoding on the house dataset
│   └── pransshu.xlsx                # House dataset used by the assignment notebook
├── merge join/
│   ├── merge join class.ipynb       # concat, merge (inner/left/right) and join demos
│   └── stress/
│       └── stress dataset.xlsx      # Stress dataset used in the join demo
└── README.md
```

## How to Run

1. Make sure Python has `pandas`, `numpy`, `scikit-learn`, and Jupyter installed (e.g. `pip install jupyter pandas numpy scikit-learn openpyxl` — `openpyxl` is pandas' Excel engine for reading `.xlsx` files).
2. From the repository root, start Jupyter:

   ```bash
   jupyter notebook
   ```

3. Open any `.ipynb` file from the browser. Note that the notebooks load data with paths relative to the notebook's own folder (e.g. `House Dataset/DPFEassignment.ipynb` reads `pransshu.xlsx`, and `merge join/merge join class.ipynb` reads `stress/stress dataset.xlsx`), so run the notebooks in place.

> Note: the final cell of `merge join/merge join class.ipynb` references a `billionaire.csv` file that is not included in this repository, so that particular cell will raise a `FileNotFoundError`.
