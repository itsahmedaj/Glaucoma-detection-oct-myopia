# Glaucoma Detection from OCT RNFL Data (Highly Myopic Cohort)

This repository contains a machine learning pipeline to detect glaucoma risk using OCT-derived RNFL thickness features in a cohort of highly myopic patients.

Because clinical ground-truth labels were unavailable, the project uses **myopia-aware OCT proxy labels** derived from internationally used RNFL criteria.

## Project structure

- `notebooks/` — main analysis notebook (data loading → proxy labels → models → evaluation)
- `data/raw/` — raw OCT RNFL feature file(s) (CSV/Excel)
- `results/` — exported tables (e.g., `model_comparison.csv`)
- `figures/` — exported plots (ROC curves, model comparisons)

## Proxy labeling (OCT-derived)

Proxy labels were defined using four OCT RNFL-based criteria:

- Global RNFL thinning (myopia-aware threshold)
- Superior RNFL thinning
- Inferior RNFL thinning
- ISNT rule violation

Eyes meeting **≥ 3** criteria were labeled as `glaucoma_proxy = 1` (glaucoma suspect).  
These labels are **not clinical diagnoses**.

## Models evaluated

- Logistic Regression (scaled features)
- Random Forest
- SVM (RBF kernel, scaled features)
- Boosting (XGBoost if available; otherwise sklearn Gradient Boosting)

## Key outputs

- Comparison table: `results/model_comparison.csv`
- Figures:
  - `figures/accuracy_comparison.png`
  - `figures/roc_auc_comparison.png`
  - `figures/false_negatives.png`
  - `figures/roc_curves.png`

## How to run

1. Create/activate your conda environment
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
