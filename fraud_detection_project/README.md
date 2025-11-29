
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

Ahmed Hisham 
13007014

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

Download from Kaggle:
🔗 [https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis](https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis)

After downloading:

1. Extract the ZIP file
2. Place all CSV files inside the **data/** folder
3. Run Notebook 01

---

## 📒 **Notebooks Overview**

### **1️⃣ 01_data_exploration_and_feature_engineering.ipynb**

* Loads and inspects all raw datasets
* Cleans missing values
* Converts date columns
* Calculates Length of Stay (LOS)
* Aggregates inpatient & outpatient claims per provider
* Merges with fraud labels
* Saves final dataset:
  **provider_features_final.csv**

---

### **2️⃣ 02_modeling.ipynb**

* Loads engineered dataset
* Performs train/test split
* Trains:

  * Logistic Regression
  * Random Forest Classifier
* Prints full classification metrics
* Saves best model + scaler
* Performs prediction testing

Random Forest performed best.

---

### **3️⃣ 03_evaluation.ipynb**

* Generates Confusion Matrix
* Generates ROC Curve
* Plots Feature Importance
* Provides interpretation of fraud indicators
* Summarizes business impact of results

---

## 📊 **Model Results Summary**

### **Random Forest (Best Model)**

| Metric                | Score |
| --------------------- | ----- |
| **Accuracy**          | 94%   |
| **Precision (Fraud)** | 68%   |
| **Recall (Fraud)**    | 67%   |
| **F1 Score**          | 0.68  |

The model detects **~2 out of 3 fraudulent providers**, which is strong given the imbalanced dataset.

---

## 🔍 **Key Fraud Indicators**

The strongest predictors of fraud were:

1. **Maximum inpatient length of stay**
2. **Total inpatient reimbursement**
3. **Number of outpatient claims**
4. **Total outpatient reimbursement**

These reflect patterns commonly associated with suspicious billing behavior.

---

## 💼 **Business Impact**

This model can:

* Prioritize provider audits
* Reduce fraudulent payments
* Improve allocation of investigative resources
* Support automated fraud surveillance systems

A recall of **67%** means the model captures most fraudulent providers, offering high practical value.

---

## ▶️ **How to Reproduce the Project**

1. Clone the repository:

   ```bash
   git clone https://github.com/Ahmed-h1sham/fraud_detection_project.git
   cd fraud_detection_project
   ```

2. Install dependencies:

3. Download the dataset from Kaggle and place it in `data/`.

4. Run the notebooks **in order**:

   * Notebook 01 → feature engineering
   * Notebook 02 → modeling
   * Notebook 03 → evaluation

---

## 🛠️ **Technologies Used**

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib / Seaborn
* Jupyter Notebook

---

## 📄 **Reports**

Located under **reports/**:

* **technical_report.pdf** — Full written analysis
* **presentation.pptx** — 10-minute presentation

---

## 📌 **Future Work**

* Use XGBoost or LightGBM
* Apply SMOTE to improve fraud recall
* Incorporate diagnosis code embeddings
* Deploy model as REST API for real-time scoring

