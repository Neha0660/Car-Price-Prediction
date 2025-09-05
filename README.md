# Car-Price-Prediction

Predicting the **selling price of used cars** using **Linear Regression** and **Lasso Regression**.  
This project explores how car attributes (year, km driven, fuel, transmission, seller type, owner) influence price and compares regularized vs. non-regularized linear models.

---

## 📌 Project Overview
- Build and evaluate regression models to estimate car prices.
- Compare **Linear Regression** (no regularization) with **Lasso Regression** (L1 regularization).
- Discuss which features matter most and how regularization affects them.

---

## 🧰 Tech Stack
- **Python**
- **Pandas, NumPy**
- **Matplotlib, Seaborn**
- **Scikit-Learn** (LinearRegression, Lasso, metrics)

---

## 📂 Dataset
- Source: **kaggle car dataset** (public used-car listings)
- File used: `car_dataset.csv`
- Columns: `name, year, selling_price, km_driven, fuel, seller_type, transmission, owner`

> Note: Categorical columns are **label-encoded**:
- `fuel`: Petrol/Diesel/CNG/LPG/Electric → 0/1/2/3/4  
- `seller_type`: Individual/Dealer/Trustmark Dealer → 0/1/2  
- `transmission`: Manual/Automatic → 0/1  
- `owner`: First/Second/Third/Fourth & Above/Test Drive Car → 0/1/2/3/4

---

## 🚀 Getting Started

### 1) Clone
```bash
git clone https://github.com/<your-username>/Car-Price-Prediction.git
cd Car-Price-Prediction
