# Model Development Report – House Price Prediction

## 1. Introduction

The objective of this project is to develop a machine learning model capable of predicting **house prices** using various property-related features. This task is formulated as a **supervised regression problem**, where the model learns the relationship between input variables (features) and the target variable (house price).

The project demonstrates:
- Data exploration & preprocessing  
- Regression modeling (scratch + scikit-learn)  
- Model evaluation using multiple metrics  
- Visualization & interpretation of results  

---

## 2. Dataset Description

- **Dataset file:** `house_data.csv`
- **Total rows:** 300  
- **Total columns:** 8  

### 2.1 Features
Typical features include:
- `Area` – built-up area in square feet  
- `Bedrooms`  
- `Bathrooms`  
- `Location` – categorical feature  
- Other dataset-specific attributes  

### 2.2 Target Variable
- **Price** – selling price of the house  

### 2.3 Data Preprocessing
Steps performed:
- Checked for and handled missing values  
- Separated numerical and categorical features  
- Encoded categorical variables using **OneHotEncoder**  
- Applied **train-test split (80% train, 20% test)**  

---

## 3. Methodology

### 3.1 Linear Regression From Scratch
A simple linear regression model was implemented manually using the **Normal Equation**:

\[
\theta = (X^TX)^{-1}X^Ty
\]

Used one numeric feature (`Area`) to predict price.  
This step helps understand the theory behind Linear Regression.

### 3.2 Linear Regression (scikit-learn)
A multivariate regression model was implemented using:
- `ColumnTransformer` for preprocessing  
- `LinearRegression()` for modeling  
- A complete pipeline to ensure clean workflow  

This model produced the metrics shown below.

---

## 4. Evaluation Metrics

Models were evaluated using:

- **MAE** – Mean Absolute Error  
- **MSE / RMSE** – Root Mean Squared Error  
- **R² Score** – Proportion of variance explained  

---

## 5. Results

### 5.1 Linear Regression (sklearn)  
The following results were extracted directly from the executed notebook:

| Metric | Value |
|--------|-----------------------|
| **MAE** | **1,431,676.63** |
| **RMSE** | **1,957,909.58** |
| **R² Score** | **0.9731** |

### Interpretation:
- **R² = 0.9731** → Model explains **97.31%** of price variation.  
- **MAE ≈ 1.43M** → Average prediction error is around 1.43 million(price unit).  
- **RMSE ≈ 1.95M** → Errors are relatively low given the dataset scale.  

These results indicate **excellent predictive performance**.

---

## 6. Visualization

The following visualizations should be added (screenshots/images):

- Dataset preview (`data.head()`)
- House price distribution histogram
- Area vs Price scatter plot
- **Predicted vs Actual Price plot** (`predictions_vs_actual.png`)

### Interpretation of Predicted vs Actual Plot:
- Points close to the diagonal line → highly accurate predictions  
- Slight deviations represent acceptable noise  
- Overall pattern confirms strong model performance  

---

## 7. Feature Importance & Interpretation

Using model coefficients or Random Forest importances (if executed):

Most influential features typically include:

1. **Area**  
2. **Location** (specific encoded categories)  
3. `Bedrooms`  
4. `Bathrooms`  

### Interpretation:
- Larger houses tend to have higher prices  
- Certain locations significantly increase predicted price  
- Bedroom count is moderately predictive but less than area  

---

## 8. Discussion

### 8.1 Strengths
- High predictive performance (R² > 0.97)  
- Proper handling of categorical and numerical data  
- Clean and modular pipeline  
- Clear visualization and interpretation workflow  

### 8.2 Limitations
- Only Linear Regression outputs confirmed in notebook  
- Additional models (Decision Tree, Random Forest) were not evaluated  
- No hyperparameter tuning  
- External market factors not considered  

### 8.3 Future Work
- Evaluate Decision Tree and Random Forest models  
- Apply GridSearchCV for hyperparameter tuning  
- Add regularized regression (Lasso, Ridge)  
- Incorporate additional real-estate features  

---

## 9. Conclusion

This project successfully implements an end-to-end machine learning workflow for **house price prediction**.  
The Linear Regression model produced excellent results:

- **MAE: 1,431,676.63**  
- **RMSE: 1,957,909.58**  
- **R² Score: 0.9731**

This demonstrates strong predictive capability and validates the usefulness of the selected features and modeling approach.

