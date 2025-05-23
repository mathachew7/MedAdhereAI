# 🧠 MedAdhereAI: Predicting Medication Adherence Risk Using Real-World Data

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**MedAdhereAI** is a research-grade machine learning pipeline built to **predict the risk of medication non-adherence** using real-world patient refill and claims data.  
It targets chronic conditions such as **diabetes** and **hypertension**, especially in resource-limited health systems.

The project focuses on interpretable AI, temporal feature engineering, and real-world clinical relevance — with the goal of publishing a peer-reviewed research paper.

---

## ✅ Project Status

> **Phase 1 Complete**  
Exploratory data analysis, binary target creation, date parsing, and refill behavior modeling have been completed.  
The dataset is now ready for feature engineering and model development.

---

## 📌 Full Project Plan

### ✅ Phase 1: Exploratory Data Analysis (Done)
- Load and inspect patient-level claim/refill data
- Analyze adherence distribution and patterns
- Convert key dates to `datetime` format
- Engineer temporal features: time between service, assessment, receipt
- Calculate `DAYS_SINCE_LAST_REFILL` per patient
- Visualize refill gap distribution
- Create `ADHERENT_BINARY` target variable

---

### 🚧 Phase 2: Feature Engineering (In Progress)
- Aggregate patient-level features:
  - Mean/max refill gap
  - Total visits, irregularity scores
  - Specialty visits (optional)
- Merge auxiliary datasets (dialysis, ophthalmology, etc.)
- Prepare modeling-ready final dataset

---

### 🔜 Phase 3: Model Building
- Train baseline models:
  - Logistic Regression
  - Random Forest
  - XGBoost
- Handle class imbalance (if needed)
- Evaluate using AUC, F1, precision/recall
- Tune and select best model

---

### 🔍 Phase 4: Model Explainability
- Use SHAP to interpret predictions
- Identify top drivers of non-adherence
- Create global and patient-level SHAP plots
- Build transparent outputs for research/publication

---

## 📁 Project Structure

```bash
MedAdhereAI/
├── dataset/
│   └── raw/                          # Raw CSVs (excluded from GitHub)
├── notebooks/
│   ├── 01_data_exploration.ipynb     # ✅ EDA + binary label creation
│   ├── 02_feature_engineering.ipynb  # ⏳ In progress
│   ├── 03_model_training.ipynb       # ⏳ Model training pipeline
│   └── 04_model_explainability.ipynb # ⏳ SHAP analysis
├── scripts/
│   ├── data_cleaning.py              # Modular cleaning logic
│   ├── feature_engineering.py
│   ├── model_utils.py
│   └── shap_explainer.py
├── reports/
│   └── figures/                      # Output plots and result images
├── requirements.txt                 # All required packages
├── .gitignore
├── README.md                        # This file
└── LICENSE                          # MIT License
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
