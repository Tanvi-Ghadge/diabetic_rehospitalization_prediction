# Diabetic Rehospitalization Prediction

A machine learning project that predicts whether a diabetic patient will be readmitted to the hospital within 30 days using structured hospital data. Built with logistic regression, Random Forest, MLP, and SVM classifiers.

---

## Project Objective

To build a reliable classification model that predicts early readmissions (<30 days) for diabetic patients, helping healthcare providers prioritize high-risk cases and reduce hospital costs.

---

## Dataset

- **Source**: [UCI ML Repository – Diabetes 130-US hospitals](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008)
- **Rows**: ~100,000+ encounters
- **Target**: `readmitted` (transformed to binary: 1 for `<30`, 0 for `NO` and `>30`)
- **Note**: The dataset was **downsampled** to reduce class imbalance, ensuring a more balanced and realistic training set (approximately 1:2 ratio for readmitted vs not).

---

## Key Features & Engineering

- **Diagnosis Mapping**: Combined `diag_1`, `diag_2`, `diag_3` into broad ICD-9 categories (e.g., Circulatory, Diabetes)
- **Drug Score**: Aggregated all drug-related features into a single `drug_score`
- **Inpatient Ratio**: Ratio of inpatient visits over total visits
- **Age Buckets to Numeric**: Converted `[30-40)` to `35`, etc.
- **Total Interventions**: Sum of procedures, medications, lab tests

---

## Models Used

| Model                 | Accuracy | Highlights                                |
|----------------------|----------|-------------------------------------------|
| Logistic Regression  | ~70%     | Balanced class weights                    |
| Random Forest        | ~75%     | Best performing; interpretable            |
| SVM                  | ~70%     | High cost on full dataset, sub-sampled    |
| MLP Classifier       | ~74%     | Tuned with hidden layers, early stopping  |

---

## Evaluation Metrics

- Accuracy
- Precision / Recall / F1-Score
- Confusion Matrix (Visualized)


---

---

## Files

- `diabetic_model.ipynb` – Final notebook with preprocessing, feature engineering, and modeling
- `README.md` – Documentation and overview

---

## How to Run

```bash
git clone https://github.com/Tanvi-Ghadge/diabetic_rehospitalization_prediction.git
cd diabetic-readmission-predictor

# Open Jupyter Notebook
jupyter notebook diabetic_model.ipynb
