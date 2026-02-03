# Machine Learning Projects

This repository collects three data‑science projects completed during a learning cohort. Each project is self-contained in its own subfolder and includes a Jupyter notebook with the working analysis and the raw dataset (where available).

Included projects
- `Apparel Sale DS` — Quarterly apparel sales analysis for AAL Q4 2020 (EDA, cleaning, visualizations, report). See `Apparel Sale DS/solution.ipynb`.
- `Avacado DS` — Avocado prices and volume analysis (time series, region comparisons). See `Avacado DS/main.ipynb`.
- `2_churn_Predict` — Customer churn prediction comparing Random Forest, XGBoost and a DNN (preprocessing, SMOTE, evaluation). See `2_churn_Predict/project_work.ipynb`.

Quick start
1. Create and activate a Python environment (recommended):

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Launch Jupyter Lab and open the notebook you want to run:

```bash
jupyter lab
```

Notes & recommendations
- The notebooks reference local CSV files included in each project folder. If you move the notebooks, update the relative paths or place the corresponding CSVs in the same folder.
- For reproducibility, create a `requirements.txt` (one is included at the repo root). Consider exporting the notebooks to HTML or adding an `environment.yml` for Conda users.
- Some notebooks perform data clipping or SMOTE resampling — these steps are documented in the respective notebooks; review them before using results for production.

Project structure

- `Apparel Sale DS/` — dataset, problem statement PDF, analysis notebook.
- `Avacado DS/` — dataset, notebook, textual report.
- `2_churn_Predict/` — notebook and supporting files.

License & contact
- Add a LICENSE file if you want to publish these projects publicly. Contact: add your email or GitHub profile in this README.
