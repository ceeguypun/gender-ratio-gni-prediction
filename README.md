# Statistics in Computer Engineering Applications (Project 1)

This repository contains the analysis and modeling code for **Project 1**, part of the Statistics in Computer Engineering Applications course at Kasetsart University.

## Project Overview
The project applies Data Science Workflows to analyze real-world datasets, focusing on two main objectives:
1.  **Classification:** Predicting **Gender Ratio Classes** using demographic data.
2.  **Regression & Clustering:** Analyzing and predicting **GNI per Capita** to understand economic disparities.

**Full Report:** You can view the detailed analysis in the PDF report:
**[Read Full Report (PDF)](report/report.pdf)**

---

## Key Results & Methodologies

### Part 1: Classification (Gender Ratio)
The goal was to classify gender ratio categories using various models.

* **Best Model:** **XGBoost Classifier**
    * **Performance:** Accuracy = 0.43, Macro F1 = 0.42.
    * **Configuration:** `learning_rate=0.05`, `n_estimators=1000`.
* **Methodology:**
    * **Preprocessing:** Imputation (Median/Mode), One-Hot Encoding. *(Note: Skewness handling was excluded for this workflow as XGBoost handles non-normal distributions well.)*
    * **Feature Selection:** Filter Methods (Low Variance, High Correlation) and Feature Importance ranking.
    * **Comparison:** Outperformed Logistic Regression (Baseline) and Random Forest Classifier.

### Part 2: Regression & Clustering (GNI per Capita)
* **Clustering (K-Means):**
    * Successfully identified **2 Clusters** (Low-Mid Income vs. High Income).
    * **Silhouette Index:** 0.703 (Indicates strong separation).
* **Regression (Prediction):**
    * **Best Model:** **Random Forest Regressor**
    * **Performance:** **R² = 0.967**, **MAPE = 11.37%**.
    * **Key Drivers:** Life Expectancy, Secure Internet Servers, and Gross Savings were the most significant predictors of GNI.

---

## Visualizations
The project includes a dashboard visualizing:
* **Correlation:** Relationship between Tertiary School Enrollment and GNI.
* **Trends:** Average GNI per capita growth over time by region.
* **Distribution:** Histogram of GNI per capita across countries.

---

## Project Structure
```text
├── data/                   # Dataset files (Raw and Processed)
├── notebooks/              # Jupyter Notebooks
│   ├── part1_gender_ratio
|   |   ├── 01_EDA.ipynb
|   |   ├── 02_Workflow1.ipynb
|   |   ├── 03_Workflow2.ipynb
|   |   ├── 04_Workflow3.ipynb
|   |   └── 05_Feature_Extraction.ipynb
│   └── part2_gni_prediction
|       ├── 01_EDA.ipynb
|       ├── 02_Clustering.ipynb
|       ├── 03_Workflow1.ipynb
|       ├── 04_Workflow2.ipynb
|       └── 05_Visualization.ipynb
├── README.md               # Project Documentation
└── requirements.txt        # Python dependencies
```

---

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/ceeguypun/gender-ratio-gni-prediction.git
cd gender-ratio-gni-prediction
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### Note
This project demonstrates the application of statistical learning techniques including **Feature Selection (RFE, Filter Methods)**, **Dimensionality Reduction (PCA, LDA)**, and **Model Evaluation (F1-score, RMSE, MAPE)**.

---