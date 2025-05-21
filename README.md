Here's a basic `README.md` draft tailored to your project files:

---

# 📉 Churn Prediction in Mobile Gaming

**ISTANBUL TECHNICAL UNIVERSITY — ISL 439E: Machine Learning in Business Applications**
**Student:** Mustafa Ercengiz – 070210255
**Instructor:** Prof. Dr. Tolga Kaya

## 📌 Project Summary

This project aims to predict **player churn** in a mobile crossword puzzle game using first-week user behavior data. Early identification of users at risk of churning enables targeted interventions such as incentives or personalized offers to increase player retention and lifetime value.

---

## 📂 Files Included

* `train_data.xlsx` — Training data with 50,000 rows and 24 columns.
* `test_data.xlsx` — Test data with 5,931 rows (without the `churn` label).
* `ODEV_YUKLEMEK_final_final_finaş.ipynb` — Main Jupyter Notebook including EDA, feature engineering, model training, and ECPI imputation.
* `prediction_xgb-Copy1.csv` — Final predictions using XGBoost classifier.
* `data_description_churndata.docx` — Column and feature descriptions.
* `ODEV_YUKLEMEK_final_final_finaş.pdf` / `MLODEV_final_inş_TOLGA HOCAM GÜZEL DERSTİ .pdf` — Project reports in PDF format.

---

## 🧪 Problem Definition

**Churn Definition:** A user is flagged as "churned" if they do **not return** to the game after the first week of installation.

### Goal

Build a machine learning model that predicts churn based on users’ first-week activity and profile features.

---

## 🛠 Features and Preprocessing

### Input Features

* Device info: `device_brand`, `device_model`, `os`
* User behavior: `duration`, `lvl_no`, `hint1_cnt`, `bonus_cnt`, `ads viewed`, `gold`, `power-ups`
* Acquisition data: `country`, `lang`, `campaignid`, `partnerid`, `ecpi`

### Target

* `churn`: Binary classification (0 = retained, 1 = churned)

### Preprocessing

* Imputed missing ECPI values using **XGBoost Regression**
* Removed high-cardinality or irrelevant features (`os`, `hint2_cnt`, `hint3_cnt`, `user_id`, etc.)
* Feature engineering for install time (`install_hour`, `install_dayofweek`, etc.)
* Handled skewed distributions and created `lvl_duration_ratio`, `log_lvl_duration_ratio`

---

## 🤖 Models Compared

* Logistic Regression
* LDA
* Decision Tree
* Random Forest
* XGBoost (🏆 **Final Model**)

### Final Performance (on validation):

* Accuracy: 85.7%
* Recall: 94.6%
* ROC AUC: 86.5%

---

## 📈 Outputs

The model was deployed to generate churn predictions on the test set. Final predictions are saved in:

```text
prediction_xgb-Copy1.csv
```

---

## 📚 References

* scikit-learn, XGBoost, pandas, matplotlib
* Lecture content from ISL 439E
* Game behavior insights inspired by Dream Games-style mobile products

---

Let me know if you want a version with visuals or export as `.md` or `.pdf`.
