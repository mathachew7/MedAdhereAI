# 🧠 MedAdhereAI: Predicting Medication Adherence Risk Using Real-World Data

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

MedAdhereAI is a research-grade machine learning pipeline built to **predict the risk of medication non-adherence** among patients with chronic conditions like **diabetes** and **hypertension**. Using real-world claims and refill data from a developing nation's healthcare system, the project aims to deliver interpretable, deployable, and publishable adherence prediction models.

---

## 📌 Key Objectives

- 📊 Forecast whether a patient will **adhere or not** to prescribed medications
- ⚙️ Engineer features from real claim-level refill data
- 🌍 Focus on **chronic conditions** in resource-constrained settings
- 🔎 Use **interpretable AI** via SHAP to understand drivers of non-adherence
- 📝 Support reproducible publication with notebooks + scripts

---

# 🧠 Current Progress (**Complete**)

## ✅ Phase 1: Exploratory Data Analysis
- Cleaned and loaded raw diabetes adherence dataset
- Created binary adherence target using domain threshold (≥ 8)
- Converted date columns to datetime for time-based feature creation
- Engineered temporal features: time between service, assess, and refill dates
- Computed refill gaps per patient and visualized refill behavior trends

## ✅ Phase 2: Feature Engineering
- Aggregated refill behavior features per patient:
  - `avg_refill_gap`, `max_refill_gap`, `total_visits`
- Merged most recent binary adherence label (`ADHERENT_BINARY`) per patient
- Enriched dataset with demographic features: `GENDER` and `AGE`
- Handled missing values:
  - Refill gaps filled with 0.0 for single-visit patients
  - Dropped intermediate date fields after transformation
- Exported cleaned dataset as `.csv` and `.pkl` for modeling

## ✅ Phase 3: Model Building & Evaluation
- Trained baseline models:
  - **Logistic Regression** (ROC AUC: 0.82)
  - **Random Forest** (ROC AUC: 0.77)
- Performed evaluation with accuracy, F1-score, and ROC AUC
- Validated model stability using 5-fold cross-validation
- Assessed probability calibration via Brier score and calibration curve
- Applied SHAP for local and global explainability
- Exported trained models for deployment (`.pkl` format)

## ✅ Phase 4: Visualization, Public Health Framing, and Real-World Deployment
- All visualizations (SHAP plots, feature importance, calibration curve) completed
- Public health impact framing and interpretation added
- Ready for research publication, deployment, and stakeholder engagement

🎉 **All project phases are complete as per the attached documentation and deliverables.**

---

## 📁 Project Structure

```bash
MedAdhereAI/
├── dataset/
│   └── raw/                          # Real-world data (CSV files, not committed)
├── notebooks/
│   ├── 01_data_exploration.ipynb     # ✅ EDA + target engineering (complete)
│   ├── 02_feature_engineering.ipynb  # ⏳ Feature aggregation (in progress)
│   ├── 03_model_training.ipynb       # ⏳ Model building
│   └── 04_model_explainability.ipynb # ⏳ SHAP analysis
├── scripts/
│   ├── data_cleaning.py              # Placeholder for modular code
│   ├── feature_engineering.py
│   ├── model_utils.py
│   └── shap_explainer.py
├── reports/
│   └── figures/                      # Output graphs, charts
├── requirements.txt                 # Python packages
├── .gitignore
├── README.md                        # This file
└── LICENSE                          # MIT License
```

---

## 🛠️ Tech Stack

- Python 3.11
- Pandas, NumPy
- scikit-learn, XGBoost
- SHAP
- Jupyter Notebook

---

## 🚀 Getting Started

```bash
# 1. Clone the repo
git clone https://github.com/mathachew7/MedAdhereAI.git
cd MedAdhereAI

# 2. Create & activate virtual environment
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

- **ADHERENT_BINARY** label (78% adherent / 22% non-adherent)
- Logistic Regression AUC: **0.82** | Random Forest AUC: **0.77**
- Brier Score: **0.1749** (well-calibrated)
- SHAP summary: `total_visits`, `AGE`, `refill_gap` as top predictors
- Logistic Regression Coefficients: Bar plot
- Random Forest Feature Importance: Bar plot
- SHAP Local Explanations: Individual-level interpretability

All outputs, visuals, and impact framing have been generated and included in the documentation.

---

## 💡 Public Health Impact

Medication non-adherence contributes to over **$300 billion** in preventable U.S. healthcare costs annually.  
This project provides an interpretable system to **flag patients at risk** of skipping essential medications using refill behavior and minimal demographic data.

This supports:
- Early risk stratification
- Targeted outreach and follow-ups
- Clinically explainable, data-driven care optimization

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Credits

- Dataset by researchers on [Mendeley Data](https://data.mendeley.com/datasets/zkp7sbbx64/2)
- Built by **Subash Yadav** for real-world predictive health research

---

## 💬 Contact

For collab or publication inquiries:  
📧 subashyadav7@outlook.com  
🔗 [LinkedIn](https://www.linkedin.com/in/mathachew7)
