# 🧠 MedAdhereAI: Predicting Medication Adherence Risk Using Real-World Data

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**MedAdhereAI** is a research-grade machine learning pipeline built to **predict the risk of medication non-adherence** using real-world patient refill and claims data.  
It targets chronic conditions such as **diabetes** and **hypertension**, especially in resource-limited health systems.

The project focuses on interpretable AI, temporal feature engineering, and real-world clinical relevance — with the goal of publishing a peer-reviewed research paper and supporting Subash Yadav’s EB-2 NIW petition.

---

## ✅ Project Status

> **Phase 3 Complete**  
Modeling, evaluation, and explainability foundation is done.

> **Phase 4 In Progress**  
Visuals being finalized and saved; public health framing complete.

---

## 📌 Full Project Plan

### ✅ Phase 1: Exploratory Data Analysis
- Loaded raw claim/refill data
- Created binary adherence label `ADHERENT_BINARY` (threshold ≥ 8)
- Parsed all dates for time-based analysis
- Engineered refill-based temporal features
- Visualized refill cycles (30/60/90 days)
- Established foundation for feature engineering

---

### ✅ Phase 2: Feature Engineering
- Aggregated patient-level behavior:
  - `avg_refill_gap`, `max_refill_gap`, `total_visits`
- Merged latest adherence label per patient
- Added demographics: `GENDER`, `AGE`
- Cleaned and imputed missing values logically
- Exported modeling-ready dataset (`.csv` and `.pkl`)

---

### ✅ Phase 3: Model Building and Evaluation
- Trained interpretable and ensemble models:
  - Logistic Regression (ROC AUC = 0.82)
  - Random Forest (ROC AUC = 0.77)
- Performed 5-fold cross-validation for robustness
- Evaluated using precision, recall, F1-score, AUC
- Checked model calibration (Brier score = 0.1749)
- Saved trained models for deployment (`.pkl` format)

---

### 🚧 Phase 4: Explainability & Impact (In Progress)
- [x] Loaded trained models and data
- [x] SHAP global + summary plots
- [x] Public health impact + NIW framing
- [ ] Logistic Regression coefficient bar chart
- [ ] Random Forest feature importance chart
- [ ] SHAP local explanation for 1 patient
- [ ] Save all visual assets to `reports/figures/`
- [ ] (Optional) Build Streamlit demo for real-world application

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

- 📈 ADHERENT_BINARY label (78% adherent / 22% non-adherent)
- ⏳ Time-based features (service gap, refill intervals)
- 📊 Refill gap distribution showing strong 30/60/90-day cycles
- 🧠 Modeling and SHAP plots coming in Phase 3 and 4

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Credits

- Dataset: [Mendeley Data – Diabetes and Hypertension Adherence](https://data.mendeley.com/datasets/zkp7sbbx64/2)
- Built and maintained by **Subash Yadav** for research and publication

---

## 💬 Contact

For collaboration, questions, or paper reference:
📧 subashyadav7@outlook.com  
🔗 [LinkedIn](https://www.linkedin.com/in/mathachew7)
