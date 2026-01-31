# 🏥 Brain Stroke Prediction using K-Nearest Neighbors (KNN)

A robust machine learning pipeline developed to predict the likelihood of a stroke based on clinical and lifestyle factors. This project focuses on handling imbalanced medical data and optimizing classification performance for healthcare decision support.

---

## 📌 Project Overview

Stroke is a leading cause of global disability and death. This project implements a **K-Nearest Neighbors (KNN)** classification model using the **Healthcare dataset (5,110 samples)**. The primary goal was to move beyond a biased "high accuracy" model to a balanced system that reliably identifies high-risk stroke patients.

Developed as part of the **COMP1827 – Introduction to AI** module at the **University of Greenwich**.

---

## ✨ Key Features & Technical Workflow

### 🛠️ Advanced Preprocessing
* **KNN Imputation:** Handled 201 missing values in the `bmi` column by leveraging similarity between data points ($k=5$) rather than simple mean-filling.
* **SMOTE Integration:** Applied **Synthetic Minority Oversampling Technique** to address significant class imbalance, generating synthetic samples for the minority (stroke) class.
* **Feature Engineering:** Utilized **Label Encoding** for categorical data (Gender, Work Type, etc.) and **StandardScaler** to normalize scales for distance-based calculations.
* **Outlier Strategy:** Deliberately retained outliers in glucose and BMI, as they represent clinically significant markers for stroke risk.

### 🧠 Model Optimization
* **Initial Bias Correction:** The baseline model achieved 94% accuracy but failed to predict actual stroke cases (only 0.09 precision for Class 1).
* **Hyperparameter Tuning:** Conducted a **Grid Search** to find the optimal configuration: `n_neighbors=3`, `weights='distance'`, and `metric='manhattan'`.
* **Feature Importance:** Performed **Permutation Importance** analysis, identifying Age and Average Glucose Level as the most critical predictors.

### 🚀 Deployment
* Implemented a real-time **Model Deployment** function (`predict_stroke`) that accepts user inputs (Age, BMI, Smoking Status, etc.) and provides a risk assessment with clinical advice.

---

## 📊 Final Performance Metrics

After optimization and balancing, the model achieved a **91% balanced accuracy**.

| Metric | Class 0 (No Stroke) | Class 1 (Stroke) |
| :--- | :--- | :--- |
| **Precision** | 0.97 | 0.86 |
| **Recall** | 0.85 | 0.97 |
| **F1-Score** | 0.90 | 0.91 |

* **5-Fold Cross-Validation:** 83.55% average accuracy.
* **Binary Cross-Entropy Loss:** 2.0030.

---

## 🧱 Technologies & Tools
* **Language:** Python
* **Libraries:** Scikit-learn, Imbalanced-learn (SMOTE), Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Environment:** Google Colab / Jupyter Notebooks

---

## 👤 Author
**Hamza Ali Khan** 🎓 BSc (Hons) Computer Science with Artificial Intelligence  
🏫 University of Greenwich  

🔗 [LinkedIn](https://www.linkedin.com/in/hamza-ali-khan-69116820b/)

---
*Note: This repository is for academic and portfolio purposes. The model's predictions are for informational use and should not replace professional medical diagnosis.*
