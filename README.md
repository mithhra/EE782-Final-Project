# EE782-Final-Project


## Models
- Baselines: Logistic Regression, RandomForest, XGBoost
- Hybrid: XGBoost feature embedding + small MLP head (trained end-to-end on engineered features)
Scripts:
- `train.py` — trains model, outputs checkpoints to `results/`
- `evaluate.py` — prints metrics and saves `results/tables/metrics.csv`

## Reproduce results
1. Install requirements: `pip install -r requirements.txt`
2. Preprocess data: `python code/preprocessing.py ...`
3. Train baseline: `python train.py --model xgboost`
4. Train hybrid: `python train.py --model hybrid`
5. Evaluate: `python evaluate.py --model hybrid`

## Results
See `results/figures` for ROC curves and `results/tables/metrics.csv` for accuracy/precision/recall/F1/AUC.

## Paper & Presentation
- Paper: `paper/main.tex` (IEEE style)
- Slides: `slides/presentation.pdf`

## Notes
Image used in paper: `/mnt/data/07527812-34d2-4fda-81ed-7c441d2a08b0.png`

## Contact
Mithu
