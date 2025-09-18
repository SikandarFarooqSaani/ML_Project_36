# 🚢 Titanic Survival Prediction (Custom 5 Features)

> ⚠️ **Note:** This response is AI-generated (except images) for clarity and ease of explanation 😊  

---

## 📌 Project Overview
The goal of this project was to predict survival on the Titanic using **5 selected features**.  
Since the dataset was **imbalanced**, two balancing methods were tested:  
- **Undersampling**  
- **SMOTE (Synthetic Minority Oversampling Technique)**  

Additionally, **Optuna** was used for hyperparameter optimization, and finally, a **stacking classifier** was built for improved performance.  

---

## 📊 Dataset Details
- **Dataset:** Custom Titanic dataset with 5 features  
- **Classes:** Survival (0 = Did not survive, 1 = Survived)  
- **Challenge:** Data imbalance (more 0’s than 1’s)  
- **Balancing methods applied:**  
  - **Undersampling (DS)**  
  - **SMOTE (SM)**  

---

## ⚙️ Models and Results

### 🔹 Logistic Regression
- **Simple:** 0.79 (24 FP, 10 FN)  
- **Undersampled:** 0.81  
- **SMOTE:** 0.80
- <img width="501" height="393" alt="36-1" src="https://github.com/user-attachments/assets/b8c67039-2bf0-42ba-b1c5-d11be02c2bfe" />

- **Optuna (SMOTE):** **0.84** (17 FP, 11 FN) ✅  
- <img width="501" height="393" alt="36-2" src="https://github.com/user-attachments/assets/820b23d8-5da6-4d11-87a8-9e9a60dc3a8a" />


---

### 🔹 AdaBoost
- **Simple:** 0.79  
- **Undersampled:** 0.77  
- **SMOTE:** 0.78  
- **Optuna (SMOTE):** 0.79 (16 FP, 20 FN)  
- <img width="501" height="393" alt="36-3" src="https://github.com/user-attachments/assets/900c4f2d-fd17-4437-99a1-1dd875fa7a5b" />


---

### 🔹 Decision Tree
- **Simple:** 0.77 (21 FP, 20 FN)  
- **Undersampled:** 0.73  
- **SMOTE:** 0.75  
- **Optuna (SMOTE):** 0.77 (similar FP/FN)  

---

### 🔹 Random Forest
- **Simple:** 0.79  
- **Undersampled:** 0.78  
- **SMOTE:** 0.81 (17 FP, 16 FN)  
- <img width="501" height="393" alt="36-4" src="https://github.com/user-attachments/assets/7c44a626-ec95-45fe-8232-37df25560d7b" />

- **Optuna (SMOTE):** **0.82** (12 FP, 19 FN)  
- <img width="501" height="393" alt="36-5" src="https://github.com/user-attachments/assets/d3dab6d4-2fce-487f-afa2-d6d36a588294" />


---

### 🔹 Gradient Boosting
- **SMOTE (Optuna):** 0.81 (16 FP, 18 FN)  
- <img width="501" height="393" alt="36-6" src="https://github.com/user-attachments/assets/3fd28b9d-ac67-4ec2-940a-a0593487d317" />


---

### 🔹 KNN
- **Simple:** 0.72 (31 FP, 19 FN)  
- **Undersampled:** 0.72  
- **SMOTE:** 0.66  
- **Optuna (DS):** 0.70 (26 FP, 26 FN)  

---

### 🔹 SVC
- **Simple:** 0.70  
- **Undersampled:** 0.65  
- **SMOTE:** 0.70  

---

## 📊 Accuracy Summary

| Model                | Accuracy |
|-----------------------|----------|
| Logistic Regression   | 0.804    |
| AdaBoost             | 0.827    |
| Decision Tree        | 0.827    |
| Random Forest        | 0.827    |
| Gradient Boosting    | 0.810    |
| KNN                  | 0.721    |

---

## 🔥 Stacking Classifier (Best Model)
- **Base Models:** RF, GB, LR, AdaBoost, DT, SVC  
- **Meta Model:** Logistic Regression  
- **Accuracy:** **0.860** 🎯  
- **Errors:** 16 FP, 9 FN  
-<img width="501" height="393" alt="36-7" src="https://github.com/user-attachments/assets/5630c671-1dee-4757-a5ad-3ad80e210947" />


---

## 🏁 Key Takeaways
- **Optuna tuning** improved Logistic Regression (0.84) and Random Forest (0.82).  
- **SMOTE balancing** worked better than undersampling.  
- **Stacking Classifier** outperformed all individual models with **0.86 accuracy**.  
- Logistic Regression with Optuna (SMOTE) was the **best single model**.  

---
