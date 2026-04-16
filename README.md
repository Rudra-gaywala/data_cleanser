# 📘 Patient Health Data Cleaning & Imputation

This project focuses on **data preprocessing and cleaning** of a healthcare dataset using multiple imputation techniques and outlier detection methods. The goal is to transform raw patient data into a clean, analysis-ready dataset.

---

## 📂 File Structure
- `pr2.ipynb` – Main notebook containing all preprocessing steps  
- `patient_health_500.csv` – Raw dataset  
- `final_data.csv` – Cleaned dataset after preprocessing  

---

## 🎯 Objective
- Handle missing values using different imputation techniques  
- Detect and treat outliers  
- Prepare a clean dataset for further analysis or modeling  

---

## 🛠️ Technologies Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Scikit-learn  
  - SimpleImputer  
  - KNNImputer  
  - IterativeImputer (MICE)  

---

## 🔍 Workflow

### 1. Data Loading
- Dataset loaded using Pandas from CSV file  
- Initial inspection using `.head()` and `.info()`

### 2. Missing Value Analysis
- Count of missing values per column  
- Percentage of missing values calculated  

### 3. Imputation Techniques

#### a. Simple Imputation
- Mean imputation for numerical column (`bmi`)  
- Most frequent imputation for categorical columns (`region`, `gender`)  

#### b. Missing Indicator + Random Sampling
- Created `_missing` indicator columns  
- Random sampling used to fill missing values  

#### c. KNN Imputation
- Applied KNNImputer with 5 neighbors  
- Used for numerical columns:
  - age  
  - bmi  
  - blood_pressure  
  - cholesterol  
  - glucose  

#### d. MICE (Iterative Imputation)
- Applied IterativeImputer for advanced imputation  
- Models relationships between features  

---

## 📊 Outlier Detection

### 1. Z-Score Method
- Applied on cholesterol and glucose  
- Threshold: Z > 3  

### 2. IQR Method
- Applied on bmi  
- Lower bound = Q1 - 1.5 × IQR  
- Upper bound = Q3 + 1.5 × IQR  

### 3. Percentile Capping
- Values capped between 1st and 99th percentile  

---

## 📈 Final Dataset
- Verified no missing values remain  
- Summary statistics generated using `.describe()`  
- Dataset exported as `final_data.csv`  

---

## 🔄 Before vs After Cleaning
- Compared dataset shape before and after cleaning  
- Statistical comparison performed  

---

## ▶️ How to Run

1. Install dependencies:
```
pip install pandas numpy matplotlib scikit-learn
```

2. Run the notebook:
```
jupyter notebook pr2.ipynb
```

---

## ⚠️ Notes & Observations
- Multiple imputation techniques are demonstrated for comparison  
- MICE provides more robust results for correlated data  
- Outlier handling improves dataset stability  
- Be cautious: overwriting dataframe during filtering may reduce dataset incorrectly  

---

## 🚀 Future Improvements
- Add visualization for missing values and outliers  
- Compare model performance before and after cleaning  
- Automate preprocessing pipeline  
