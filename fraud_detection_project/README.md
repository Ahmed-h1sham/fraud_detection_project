# **Healthcare Provider Fraud Detection Project**

Machine Learning · Fraud Analytics · CMS Claims Data

---

## 📌 **Project Overview**

Healthcare fraud costs the industry billions of dollars every year.
This project builds a complete end-to-end machine learning pipeline to detect **fraudulent healthcare providers** using Medicare claim patterns.

The dataset comes from the **CMS Healthcare Provider Fraud Detection Challenge** and includes:

* Beneficiary-level details
* Inpatient claims
* Outpatient claims
* Provider fraud labels

We engineered provider-level features, trained multiple models, and evaluated their effectiveness at predicting **PotentialFraud (Yes/No)**.

---

## 👥 **Team Members**

**Ahmed Hisham**
ID: **13007014**

---

## 🗂️ **Repository Structure**

```
fraud_detection_project/
│
├── README.md
│
├── data/
│   └── README.md   (instructions to download dataset)
│
├── notebooks/
│   ├── 01_data_exploration_and_feature_engineering.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_evaluation.ipynb
│
├── reports/
│   ├── technical_report.pdf
│   └── presentation.pptx
│
└── provider_features_final.csv   (generated in Notebook 01)
```

---

## 📥 **Dataset Download Instructions**

The dataset is too large to upload to GitHub.

Download it from Kaggle:
🔗 [https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis](https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis)

After downloading:

1. Extract the ZIP
2. Move all CSVs into the **data/** folder
3. Run Notebook 01

---

## ▶️ **How to Reproduce the Project**

### **1️⃣ Clone the repository**

```bash
git clone https://github.com/Ahmed-h1sham/fraud_detection_project.git
cd fraud_detection_project
```

---

### **2️⃣ Create and activate a virtual environment (`.venv`)**

#### **Windows (PowerShell)**

```bash
python -m venv .venv
.venv\Scripts\Activate
```

#### **Mac / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

### **3️⃣ Install dependencies**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

---

### **4️⃣ Launch Jupyter Notebook**

```bash
jupyter notebook
```

This opens Jupyter in your browser.

---

### **5️⃣ Run the project notebooks in order**

1 → `01_data_exploration_and_feature_engineering.ipynb`
2 → `02_modeling.ipynb`
3 → `03_evaluation.ipynb`

---

## 📒 **Notebooks Overview**

### **1️⃣ 01_data_exploration_and_feature_engineering.ipynb**

* Loads and inspects raw datasets
* Cleans missing values
* Converts date fields
* Computes LOS (Length of Stay)
* Aggregates inpatient & outpatient claims by provider
* Merges with fraud labels
* Saves `provider_features_final.csv`

---

### **2️⃣ 02_modeling.ipynb**

* Loads engineered dataset
* Creates train/test split
* Trains:

  * Logistic Regression
  * Random Forest Classifier
* Prints full model metrics
* Saves best model + scaler

Random Forest performed best.

---

### **3️⃣ 03_evaluation.ipynb**

* Plots Confusion Matrix
* Plots ROC Curve
* Displays Feature Importance
* Interprets results
* Discusses impact of fraud detection

---

## 📊 **Model Results Summary**

### ⭐ **Random Forest (Best Model)**

| Metric                | Score |
| --------------------- | ----- |
| **Accuracy**          | 94%   |
| **Precision (Fraud)** | 68%   |
| **Recall (Fraud)**    | 67%   |
| **F1 Score**          | 0.68  |

The model detects **~2 out of 3 fraudulent providers**, strong performance for imbalanced data.

---

## 🔍 **Key Fraud Indicators**

1. Maximum inpatient LOS
2. Total inpatient reimbursement
3. Outpatient claim count
4. Total outpatient reimbursement

These align with known fraud patterns.

---

## 💼 **Business Impact**

This model enables:

* Faster provider audits
* Better allocation of investigative resources
* Reduced fraudulent payments
* Real-time fraud surveillance potential

---

## 🛠️ **Technologies Used**

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 📄 **Reports**

Located under **reports/**:

* `technical_report.pdf` — Full documentation
* `presentation.pptx` — 10-minute presentation

---

## 📌 **Future Work**

* XGBoost / LightGBM
* SMOTE balancing
* NLP on diagnosis codes
* Deploy model as an API
