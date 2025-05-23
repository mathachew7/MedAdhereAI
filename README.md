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

## 🧠 Current Progress (Phase 1 Complete)

Phase 1 focused on data exploration and label creation:

- ✅ Cleaned and loaded raw diabetes adherence dataset
- ✅ Created binary adherence target using domain threshold (≥ 8)
- ✅ Converted all date columns for time-based analysis
- ✅ Engineered features: time between service and assess/receive
- ✅ Computed refill gaps per patient using `SERVICE DATE`
- ✅ Visualized refill gap distribution (e.g., 30/60/90 day cycles)
- ✅ Confirmed readiness for feature aggregation and modeling

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

## 🧪 Sample Output Preview

- ✅ ADHERENCE target engineered using refill levels
- ✅ SHAP plots showing top risk drivers
- ✅ ROC AUC & confusion matrix from multiple classifiers

> Visuals and modeling results will be added in future phases.

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
