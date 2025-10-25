// ...existing code...
# customer_segmentation

This repository contains a simple customer segmentation project that explores, preprocesses, and clusters mall customer data to produce customer segments and a base clustering model.

## Contents
- [Data files](data)
- Notebooks:
  - [notbooks/01- Data Exploration.ipynb](notbooks/01- Data Exploration.ipynb)
  - [notbooks/02- Data Cleaning & Feature Engineering.ipynb](notbooks/02- Data Cleaning & Feature Engineering.ipynb)
  - [notbooks/03- Data Preprocessing and Base Model.ipynb](notbooks/03- Data Preprocessing and Base Model.ipynb)
- Scripts: [scripts/test.py](scripts/test.py)
- Project helpers: [setup_guide.md](setup_guide.md), [.vscode/settings.json](.vscode/settings.json)
- Requirements: [requirements.txt](requirements.txt)

## Purpose
Use the Mall Customers dataset to:
1. Explore and visualize the data.
2. Clean and engineer features.
3. Preprocess and run baseline clustering (KMeans, DBSCAN).
Notebooks show the step-by-step workflow.

## Quickstart

1. Create a Python 3.11 virtual environment and activate it (see [setup_guide.md](setup_guide.md)).
2. Install dependencies:
```sh
$ python -m pip install -r requirements.txt
```
3. Open and run the notebooks in order:
   - [notbooks/01- Data Exploration.ipynb](notbooks/01- Data Exploration.ipynb)
   - [notbooks/02- Data Cleaning & Feature Engineering.ipynb](notbooks/02- Data Cleaning & Feature Engineering.ipynb)
   - [notbooks/03- Data Preprocessing and Base Model.ipynb](notbooks/03- Data Preprocessing and Base Model.ipynb)

If running inside this dev container, start Jupyter and open in your browser:
```sh
$ jupyter lab --no-browser
$ $BROWSER http://localhost:8888
```

## Data
- Raw: [data/Mall_Customers.csv](data/Mall_Customers.csv)
- Semi-cleaned used in notebooks: [data/semi_cleaned_Mall_Customers.csv](data/semi_cleaned_Mall_Customers.csv)

## Notebooks and key variables
- The main preprocessing and base model are in [notbooks/03- Data Preprocessing and Base Model.ipynb](notbooks/03- Data Preprocessing and Base Model.ipynb). Key notebook variables:
  - [`df`](notbooks/03- Data Preprocessing and Base Model.ipynb) — main DataFrame loaded from CSV.
  - [`transformer`](notbooks/03- Data Preprocessing and Base Model.ipynb) — ColumnTransformer used to prepare features.
  - [`pipe`](notbooks/03- Data Preprocessing and Base Model.ipynb) — Pipeline combining preprocessing and model.
  - [`km`](notbooks/03- Data Preprocessing and Base Model.ipynb) — KMeans model instance used as baseline.
  - [`X_prepared`](notbooks/03- Data Preprocessing and Base Model.ipynb) — preprocessed feature matrix used for clustering.

## Running the base model (summary)
- Preprocessing: numeric features are scaled with StandardScaler via `transformer`.
- Clustering: KMeans is fit with `n_clusters=5` by default in the notebook; silhouette scores for different K are computed.
- DBSCAN is also demonstrated for density-based clustering.

## Scripts
- [scripts/test.py](scripts/test.py) — example script (inspect and run as needed).

## Notes
- See [setup_guide.md](setup_guide.md) for environment setup instructions.
- Dependencies listed in [requirements.txt](requirements.txt).
- Notebooks contain visualization outputs and intermediate results; run cells sequentially for reproducible results.

## Contact
Use the repository files above to explore code and reproduce experiments.