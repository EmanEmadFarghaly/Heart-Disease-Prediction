# ❤️ Heart Disease Prediction System (End-to-End ML Project)

## 📌 Overview
This project presents a complete **Machine Learning pipeline** for predicting heart disease using the UCI Heart Disease dataset.

The system not only predicts whether a patient is at risk, but also provides **interpretable explanations** using SHAP, making it suitable for real-world decision support.

---

## 🚀 Key Features
- Full ML pipeline (Preprocessing → Modeling → Evaluation → Deployment)
- Multiple model comparison (LR, DT, RF, SVM)
- Feature Selection + PCA
- Hyperparameter tuning (GridSearch & RandomSearch)
- Explainable AI (SHAP 🔥)
- Interactive **Streamlit Dashboard**
- Model deployment-ready with saved pipeline

---

## 📊 Dataset
- Source: UCI Heart Disease Dataset
- Samples: 303
- Features: 13 clinical features

---

## 🧹 Data Preprocessing
- Handled missing values (`ca`, `thal`)
- Outlier treatment using IQR capping
- Feature scaling (StandardScaler)
- Target transformation (binary classification)
- Exploratory Data Analysis (EDA)

---

## 📉 PCA (Dimensionality Reduction)
- Components selected: **12**
- Variance retained: **≥ 95%**

---

## 🔍 Feature Selection
Selected based on Random Forest + Chi-Square:
['thal', 'ca', 'cp', 'exang', 'thalach', 'oldpeak', 'age', 'sex']

## 📊 Results Summary

| Dataset | Model | Accuracy | Precision | Recall | F1 | AUC |
|--------|------|---------|----------|--------|----|-----|
| Clean | Logistic Regression | 0.869 | 0.813 | 0.929 | 0.867 | 0.947 |
| Clean | Decision Tree | 0.820 | 0.758 | 0.893 | 0.820 | 0.825 |
| Clean | **Random Forest ⭐** | **0.885** | 0.818 | **0.964** | **0.885** | **0.959** |
| Reduced | Logistic Regression | 0.869 | 0.813 | 0.929 | 0.867 | 0.935 |
| Reduced | Decision Tree | 0.803 | 0.735 | 0.893 | 0.806 | 0.810 |
| Reduced | Random Forest | 0.852 | 0.806 | 0.893 | 0.847 | 0.956 |
| Reduced | SVM | 0.885 | 0.839 | 0.929 | 0.881 | 0.944 |
| PCA | Logistic Regression | 0.869 | 0.813 | 0.929 | 0.867 | 0.948 |
| PCA | Decision Tree | 0.803 | 0.750 | 0.857 | 0.800 | 0.807 |
| PCA | Random Forest | 0.885 | 0.862 | 0.893 | 0.877 | 0.948 |
| PCA | SVM | 0.869 | 0.833 | 0.893 | 0.862 | 0.924 |

---

## 🏆 Best Model

- **Model:** Random Forest  
- **Dataset:** Clean Data  
- **Accuracy:** 88.5%  
- **AUC:** 0.959  

---

## ⚙️ Hyperparameter Tuning

### 🔹 Baseline
- Accuracy: **0.885**

### 🔹 GridSearch
- Accuracy: **0.901**  
- Best Parameters:
```python
{'max_depth': 5, 'min_samples_leaf': 2, 'min_samples_split': 5, 'n_estimators': 100}


### 🔹 RandomSearch ⭐ (Best)
- Accuracy: **0.918**
- Best Parameters:
```python
{'n_estimators': 50, 'min_samples_split': 10, 'min_samples_leaf': 2, 'max_depth': 5}

---

## 🔍 Unsupervised Learning (Clustering)

To explore hidden patterns in the dataset, unsupervised learning techniques were applied:

### 📌 K-Means Clustering
- Used the **Elbow Method** to determine optimal number of clusters
- Optimal K ≈ 2–3 (based on SSE curve)
- Clusters show separation between low-risk and high-risk patients

### 📌 Hierarchical Clustering
- Applied **Ward linkage**
- Visualized using a dendrogram
- Provided insight into hierarchical relationships between patient groups

### 📊 Cluster vs Actual Labels
- Compared cluster assignments with actual disease labels
- Observed partial alignment between clusters and target classes
- Indicates that patient groups naturally form meaningful patterns

---

## 💡 Insights from Clustering

- Patients tend to group into **distinct risk categories**
- Some clusters strongly correlate with heart disease presence
- Confirms that features like `cp`, `thalach`, and `oldpeak` drive natural grouping

---

## Explainable AI (SHAP)

The model is enhanced with **SHAP** to:
- Explain individual predictions
- Identify top contributing features
- Provide global feature importance

This makes the system **transparent and trustworthy**.

---

## Key Insights from Data

- **Chest Pain Type (cp)** is one of the strongest indicators of heart disease
- Higher **oldpeak** values are strongly associated with increased risk
- Lower **maximum heart rate (thalach)** is linked to higher probability of disease
- **Number of vessels (ca)** significantly impacts prediction
- Males show slightly higher risk compared to females

---

## Streamlit Dashboard

### Features
- Real-time prediction
- Risk probability visualization
- SHAP explanation for each prediction
- Dataset comparison visualization

---

## Model Export

- Final pipeline saved using `joblib`
- Includes:
  - Preprocessing
  - Encoding
  - Scaling
  - Model

---

## Future Improvements

- Add deep learning models
- Add patient history tracking
- Improve UI with advanced visualization

---

## Conclusion

This project demonstrates a complete ML workflow:  
**From raw data → to prediction → to an explainable decision system.**
​

```python
['thal', 'ca', 'cp', 'exang', 'thalach', 'oldpeak', 'age', 'sex']
