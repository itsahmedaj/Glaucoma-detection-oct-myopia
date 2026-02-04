# Data description

This project uses OCT-derived RNFL measurements for glaucoma detection
in a cohort of highly myopic patients.

## Raw data
- Located in: `data/raw/`
- Format: CSV / Excel
- Contents:
  - Global RNFL thickness
  - Sector-wise RNFL measurements
  - TSNIT quadrant averages
- No clinical ground-truth glaucoma labels are available.

⚠️ Raw data files must not be modified.

## Proxy labels
Glaucoma labels are derived using proxy rules based on internationally
used RNFL thresholds adapted for highly myopic eyes.

These proxy labels are **not clinical diagnoses** and are used solely
for exploratory and methodological evaluation.
