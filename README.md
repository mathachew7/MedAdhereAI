# 🧠 MedAdhereAI: Predicting Medication Adherence Risk Using Real-World Data

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**MedAdhereAI** is a research-grade machine learning pipeline built to **predict the risk of medication non-adherence** using real-world patient refill and claims data.  
It targets chronic conditions such as **diabetes** and **hypertension**, especially in resource-limited health systems.

The project focuses on interpretable AI, temporal feature engineering, and real-world clinical relevance — with the goal of publishing a peer-reviewed research paper.

---

## ✅ Project Status

**Phase 1:** ✅ Completed  
**Phase 2:** ✅ Completed  
**Phase 3:** ✅ Completed  
**Phase 4:** 🚧 In Progress (visuals and impact framing being finalized)

---

## 📌 Full Project Plan

### ✅ Phase 1: Exploratory Data Analysis
- Loaded raw claim/refill data
- Created binary adherence label (`ADHERENT_BINARY`, threshold ≥ 8)
- Parsed date columns for time-based feature creation
- Engineered refill-related features like service-assess gaps
- Calculated `DAYS_SINCE_LAST_REFILL`
- Visualized refill behavior (30/60/90-day cycles)

### ✅ Phase 2: Feature Engineering
- Aggregated patient-level features:
  - `avg_refill_gap`, `max_refill_gap`, `total_visits`
- Merged most recent `ADHERENT_BINARY` label
- Added `AGE` and `GENDER` demographic features
- Handled missing values (logical imputation and column drops)
- Exported cleaned data (`final_model_data.csv`, `.pkl`)

### ✅ Phase 3: Model Building and Evaluation
- Models trained:
  - Logistic Regression (ROC AUC = **0.82**)
  - Random Forest (ROC AUC = **0.77**)
- Evaluated using:
  - Accuracy, F1-score, Precision, Recall
  - ROC AUC + Cross-validation
  - Brier Score = **0.1749** (well-calibrated)
- Exported `.pkl` models for reuse and explainability

### 🚧 Phase 4: Explainability & Impact
- [x] SHAP summary plot complete
- [x] Model calibration and Brier evaluation
- [x] NIW public health impact framing
- [x] Logistic regression coefficient bar chart
- [x] Random forest feature importance plot
- [ ] SHAP local explanation (1 patient)
- [ ] Export all visuals to `reports/figures/`
- [ ] Optional Streamlit app for real-time prediction

---

## 📁 Project Structure

```bash
MedAdhereAI/
├── dataset/
│   ├── raw/
│   └── processed/
│       ├── final_model_data.csv
│       └── final_model_data.pkl
├── model/
│   ├── logistic_regression_model.pkl
│   └── random_forest_model.pkl
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_model_explainability_and_impact.ipynb
├── reports/
│   └── figures/
├── scripts/
│   └── (optional reusable code blocks)
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 🛠️ Tech Stack

- Python 3.11
- pandas, numpy
- scikit-learn, xgboost
- SHAP (for interpretability)
- matplotlib, seaborn
- Jupyter Notebook

---

## 🚀 Getting Started

```bash
# 1. Clone the repo
git clone https://github.com/mathachew7/MedAdhereAI.git
cd MedAdhereAI

# 2. Create and activate virtual environment
python3.11 -m venv .venv
source .venv/bin/activate

# 3. Install dependencies
pip install --upgrade pip
pip install -r requirements.txt

# 4. Launch notebooks
jupyter notebook
```

---

## 📊 Sample Outputs

- ADHERENT_BINARY label (78% adherent / 22% non-adherent)
- Logistic Regression AUC: 0.82 | Random Forest AUC: 0.77
- Brier Score: 0.1749 (well-calibrated)
- SHAP summary shows total_visits, AGE, refill_gap as top predictors
- Additional plots (coefficients, RF importance, local SHAP) coming soon

---

## 💡 Public Health Impact
Medication non-adherence contributes to over $300 billion in preventable U.S. healthcare costs annually.
This project provides an interpretable system to flag patients at risk of skipping essential medications using refill behavior and minimal demographic data.

This supports:
- Early risk stratification
- Targeted outreach and follow-ups
- Clinically explainable, data-driven care optimization

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
Use freely with citation.

---

## 🙌 Credits

- Dataset: [Mendeley Data – Diabetes and Hypertension Adherence](https://data.mendeley.com/datasets/zkp7sbbx64/2)
- Built and maintained by **Subash Yadav** for research and publication

---

## 💬 Contact

For collaboration, questions, or paper reference:
📧 subashyadav7@outlook.com  
🔗 [LinkedIn](https://www.linkedin.com/in/mathachew7)
