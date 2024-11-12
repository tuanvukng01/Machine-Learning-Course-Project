# Predicting Apartment Rental Offers in Germany

## Project Overview

This project aims to predict apartment rental prices in Germany using machine learning techniques, specifically Polynomial Regression and Random Forest Regression. Given Germany's active real estate market, particularly in tech hubs that attract students and professionals, finding suitable housing can be a complex process. By predicting rental costs accurately, this project can provide valuable insights to newcomers looking to budget for living expenses.

## Problem Formulation

The goal of this project is to model and predict apartment rental prices in Germany based on specific rental attributes. Given the market's complexity, we focused on a subset of features most influential in determining rental costs. The project uses pre-pandemic data from Kaggle's "Immoscout24" dataset, ensuring a stable historical foundation for predictions.

## Dataset

The original dataset contains over 200,000 records with 49 attributes, though we refined it to 3,000 data points and six key features for efficient processing and clearer interpretability. The features selected for this project are:
- **ServiceCharge**: Auxiliary costs (e.g., electricity or internet) in €
- **LivingSpace**: Size of the rental property in square meters
- **BaseRent**: Rent excluding heating and other service charges (Kaltmiete, in €)
- **PictureCount**: Number of images in the listing
- **PriceTrend**: Price trend as calculated by Immoscout24
- **Date**: Date of data scraping (month, year)

The target variable, **TotalRent** (Warmmiete, including all service charges), is what we aim to predict.

## Methodology

### 1. Data Preprocessing
After selecting relevant features, the dataset was split into training, validation, and test sets with ratios of 0.6, 0.2, and 0.2, respectively. This split supports model evaluation without overfitting.

### 2. Models Used
Two regression models were implemented:
   - **Polynomial Regression**: Polynomial regression was selected after initial analysis showed a non-linear relationship between features and rental prices. Various polynomial degrees were tested to balance prediction accuracy and model complexity.
   - **Random Forest Regression**: Given the non-linear nature of the problem, we also implemented Random Forest, an ensemble method that can capture complex relationships without extensive data preprocessing. Different tree depths were evaluated to optimize model performance.

### 3. Evaluation Metrics
**Mean Squared Error (MSE)** was chosen as the evaluation metric for both models, balancing penalization of large errors with interpretability for continuous prediction.

## Results

### Model Comparison
Polynomial Regression with a degree of 2 outperformed Random Forest Regression in terms of validation error, making it the final model. The best results achieved were:
   - **Polynomial Regression (degree 2)**: Validation MSE of 0.00068
   - **Random Forest Regression**: Best MSE with a depth of 11 was 0.0010265

These results indicate that Polynomial Regression provided a closer fit to the data, although both models performed comparably well.

### Test Performance
The final Polynomial Regression model achieved a test set MSE of 0.00099298, demonstrating acceptable performance within tolerance limits.

## Conclusion

This project successfully modeled apartment rental prices in Germany using machine learning. The Polynomial Regression model with degree 2 was selected as the optimal model due to its performance in validation and test sets. Future improvements could include exploring regularization techniques or adding more features to further improve accuracy, though such additions may increase computational complexity.

## References
1. Data source: [Immoscout24 on Kaggle](https://www.kaggle.com/).
2. Scikit-Learn documentation for [LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) and [RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html).

## Code Appendix
The complete code for data preprocessing, model training, and evaluation can be found in the repository.

---

This project serves as a valuable resource for anyone interested in understanding and navigating the German real estate market, especially newcomers to the country.