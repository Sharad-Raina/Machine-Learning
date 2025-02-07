# Hospital Length of Stay Prediction Project

## 📌 Project Overview  
This project predicts **Length of Stay (LOS)** for hospital patients using healthcare metrics like re-admission counts, glucose levels, and kidney function. The goal is to optimize resource allocation and improve patient care by anticipating hospitalization duration. The dataset includes 100k+ patient records with 27+ features.

---

## 🛠️ Tools & Techniques  
- **R** (tidyverse, caret, randomForest, gbm)  
- **Data Prep**: Missing value imputation, outlier removal, feature engineering  
- **Advanced Modeling**: PCA, hyperparameter tuning, ensemble learning  
- **Validation**: 50-fold cross-validation, RMSE, R²  

---

## 🔍 Methodology  
### **3 Iterative Phases**  
1. **Basic Data Prep**  
   - Minimal preprocessing (date conversion, outlier retention).  
   - Models: Linear Regression (LR), Stepwise AIC, Random Forest (RF), Gradient Boosting (GBM).  

2. **Advanced Data Prep**  
   - Feature engineering (weekend admission flags, kidney status, comorbidity index).  
   - Outlier removal, standardization, missing value imputation.  
   - Tuned models with cross-validation.  

3. **PCA Transformation**  
   - Reduced 27 features → 9 principal components (91% variance retained).  
   - Re-evaluated models on PCA-transformed data.  

4. **Ensemble Model**  
   - Combined best-performing LR, RF, and GBM models with weighted averaging.  

---

## 📊 Key Findings  
### **Model Performance**  
| Model Type          | Basic Data Prep (RMSE) | Advanced Data Prep (RMSE) | PCA-Transformed (RMSE) |  
|---------------------|------------------------|---------------------------|------------------------|  
| Linear Regression   | 1.19                  | 1.05                     | **0.72**              |  
| Random Forest       | 0.49                  | **0.42**                 | 0.38                  |  
| Gradient Boosting   | 0.63                  | 0.58                     | 0.51                  |  
| **Ensemble Model**  | -                     | **0.46**                 | -                      |  

- **Best Model**: Tuned Random Forest (RMSE = 0.42, R² = 0.99).  
- **PCA Impact**: Improved LR performance by 40% (RMSE ↓ from 1.05 → 0.72).  
- **Key Drivers**: Re-admission count (r = 0.75 with LOS), comorbidity index.  

---

## 🚀 Insights & Recommendations  
1. **Resource Allocation**:  
   - Patients with >2 re-admissions stay 3.8x longer (avg LOS = 8.2 days).  
2. **Peak Admissions**:  
   - Weekend admissions (15% of total) correlate with 12% longer stays.  
3. **Clinical Focus**:  
   - Renal impairment increases LOS by 4.1 days (vs. normal kidney function).  

---

