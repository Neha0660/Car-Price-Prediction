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

## 🧪 Models & Results

### Train/Test Split
- 80% train / 20% test (random_state=2)

### Performance (R² score)
| Model               | Train R² | Test R² |
|---------------------|----------|---------|
| Linear Regression   | 0.4283   | 0.4918  |
| Lasso Regression    | 0.4283   | 0.4918  |

**Observations:**
- Both Linear Regression and Lasso Regression gave almost identical R² scores (~0.43 on training, ~0.49 on testing).  
- Lasso did not shrink any coefficients to zero, meaning all features contributed to predictions.   
- The scatter plots of Actual vs Predicted prices showed that predictions followed the general trend but with noticeable spread due to dataset noise.

---

## 📊 Visualizations
The project includes scatter plots to compare **Actual vs Predicted** prices:

- **Training Data** → Checks how well the model fits known data.  
- **Testing Data** → Evaluates generalization to unseen cars.  

> Example: In both Linear and Lasso, points roughly follow the diagonal line (actual = predicted), but with some spread due to dataset noise.

---

## 🔎 Feature Coefficients (Linear vs Lasso)

| Feature        | Linear Coef | Lasso Coef |
|--------------- |------------:|-----------:|
| `year`         | 39931.20    | 39931.48   |
| `km_driven`    |    -0.5888  |    -0.5888 |
| `fuel`         | 210230.59   | 210227.18  |
| `seller_type`  |  93388.71   |  93385.98  |
| `transmission` | 865301.31   | 865291.21  |
| `owner`        | -13243.47   | -13241.58  |

**Insights:**
- **Transmission** has the largest positive impact (automatic cars → higher price).  
- **Fuel type** and **seller type** also significantly affect resale price.  
- **Year** shows that newer cars fetch better value.  
- **Owner count** and **km driven** reduce the price, as expected.  
- Lasso coefficients are almost identical to Linear → it didn’t eliminate any features, confirming all were relevant.

---

## 🧭 Future Work
- Add **feature engineering** (e.g., extract car brand/model from `name`).  
- Try **advanced models**: Random Forest, XGBoost, CatBoost for higher accuracy.  
- Perform **hyperparameter tuning** (e.g., adjust Lasso `alpha`).  
- Deploy a **Streamlit/Flask web app** to predict car prices interactively.  
- Compare more regularization techniques (Ridge, ElasticNet).  

---

## ✅ Conclusion

- All features in the dataset (`year, km_driven, fuel, seller_type, transmission, owner`) are relevant for predicting car prices.  
- **Automatic transmission**, **fuel type**, and **manufacture year** are the strongest positive drivers of price, while **higher km driven** and **multiple owners** reduce resale value.  
- Linear and Lasso regression performed similarly, showing that regularization was not critical for this dataset.  
- This project highlights how even simple regression models can provide insights into key factors influencing car prices.  
- For higher accuracy, future work could explore non-linear models like **Random Forest** or **XGBoost**, along with advanced feature engineering.
