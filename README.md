# 🎬 Movie Revenue Prediction Project
![I want a movie clipper board on some money (1)](https://github.com/user-attachments/assets/346a6a1f-ebe0-4110-a780-ccf6e60e8710)

## 📌 Project Overview

This project aims to predict the **revenue** of a movie using various features such as budget, popularity, vote count, runtime, release month, and genre. The model was developed using the **TMDB 5000 Movie Dataset**. The ultimate goal is to understand the key drivers of movie revenue and build a robust model for real-world forecasting.

---

## 🧠 Business Understanding

In the film industry, knowing how much revenue a movie might earn before release can inform critical decisions—such as production budget, marketing efforts, and distribution strategy. This project helps answer:

- What are the strongest predictors of movie revenue?
- Can we estimate a film’s earning potential early on?
- How reliable is our prediction model?

---

## 🧹 Data Preprocessing

Key preprocessing steps included:

- **Merging datasets**: Combined movie and credits data.
- **Handling missing values**: Dropped or imputed where necessary.
- **Feature engineering**:
  - Extracted `release_month`.
  - Binned `runtime` into short, average, long categories.
  - Created dummy variables for genres.
- **Standardization**: Applied to numerical features for better model performance.
- **Log transformation**: Applied to the `revenue` target to address skewness and improve regression performance.

---

## 📈 Modeling Approach

- Used **Ordinary Least Squares (OLS)** Linear Regression as the baseline model.
- Improved model through:
  - Feature transformations
  - Dummy variable encoding
  - Iterative feature selection and significance testing
  - Interaction term experimentation
- Conducted **train-test split** for robust performance checks.

---

## 📊 Model Evaluation

### Metrics:
- **Mean Absolute Error (MAE)**
- **R-squared (R²)** for model fit

#### Results:
- **Train MAE (log-transformed)**: ~1.03
- **Test MAE (log-transformed)**: ~1.09
- **Mean Absolute Oercentage Error**: ~9.08% 
- Revenue recovery (after inverse transformation) showed the model tends to underestimate very high revenue films but captures mid-range patterns reasonably well.

---

## Insights

- **Budget**, **popularity**, and **vote_count** were strong positive predictors.
- Certain **genres** like *Action*, *Thriller*, and *Drama* negatively impacted revenue, while *Adventure* and *Comedy* were associated with higher revenue.
- **Runtime** length categories added significant predictive power when converted to dummies.
- **release_seasons** such as like `summer season` had positive effects on the overall revenue.

---

## Limitations & Considerations

- Model performance on high-revenue movies could be improved.
- Genre dummies could be further refined with subgenre analysis.
- Future work could explore non-linear models (e.g., Random Forests, XGBoost).

---

## Tools & Technologies

- Python
- pandas, NumPy
- statsmodels
- scikit-learn
- matplotlib, seaborn
