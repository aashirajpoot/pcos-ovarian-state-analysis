# PCOS Ovarian Ultrasound Analysis

Academic team project exploring whether structured ovarian ultrasound measurements can help distinguish PCOS and non-PCOS cases. The analysis engineers an Ovarian State Representation (OSR), compares machine-learning classifiers, and uses feature attribution and clustering for exploratory interpretation.

## Repository contents

- `notebooks/pcos_ovarian_analysis.ipynb` - cleaned analysis workflow adapted from the project notebooks. Outputs are cleared; the source CSV is intentionally not included.
- `requirements.txt` - Python packages used by the notebook.

## Data

The notebook expects an authorized local copy of `PCOS_data.csv` in the repository root. The dataset is not distributed here because it contains patient-level clinical records. Do not commit the dataset or any row-level exports. The `.gitignore` excludes common dataset and output files.

## Run

1. Create and activate a Python environment.
2. Install dependencies with `pip install -r requirements.txt`.
3. Place an authorized copy of `PCOS_data.csv` in the repository root.
4. Open and run `notebooks/pcos_ovarian_analysis.ipynb`.

## Analysis outline

1. Clean column names and parse the target and ovarian ultrasound measures.
2. Engineer four descriptors: total follicles, follicle imbalance, average follicle size, and ovarian density index.
3. Split the data before scaling or oversampling. Scaling and SMOTE are fitted only within each training fold to reduce evaluation leakage.
4. Compare Random Forest, XGBoost, CatBoost, and a soft-voting ensemble on a held-out test set.
5. Use SHAP to inspect model feature contributions and K-means to explore ovarian measurement patterns.

## Limitations

This is an academic analysis of a single structured dataset, not a clinically validated diagnostic system. The risk probabilities and clusters are exploratory outputs and should not be used for medical decisions. Results should be reported only after rerunning the corrected workflow with the authorized dataset.

## Credits

This was completed as an academic team project.
