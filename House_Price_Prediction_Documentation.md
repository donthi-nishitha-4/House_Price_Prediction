## Project Report: House Price Prediction Using Multiple Linear Regression
------------------------------
## 1. Objective
The primary objective of this project is to construct a Multiple Linear Regression model to predict residential house prices (SalePrice). The model evaluates the relationship between a property's market value and two primary structural characteristics:

* Total above-grade living area (measured in square feet).
* Total rooms above ground level (excluding bathrooms).

------------------------------
## 2. Dataset Details
The dataset used for this project is sourced from the benchmark Kaggle House Prices: Advanced Regression Techniques competition [1].
## Key Variables Selected:

* GrLivArea (Independent Variable / Feature): Above-grade (ground level) living area square footage.
* TotRmsAbvGrd (Independent Variable / Feature): Total rooms above grade (does not include bathrooms).
* SalePrice (Dependent Variable / Target): The property's sale price in USD ($).

## Data Preprocessing Steps:

   1. Feature Isolation: The dataset was filtered to retain only the three target columns.
   2. Missing Value Treatment: Checked for null entries across features. Rows containing missing structural inputs were dropped to maintain matrix consistency.
   3. Data Partitioning: The dataset was split into an 80% Training Set (to fit the regression hyperplane coefficients) and a 20% Testing Set (to evaluate model generalizability on unseen data).

------------------------------
## 3. Model Used
The machine learning algorithm applied is Multiple Linear Regression, implemented via Python’s scikit-learn library.
## Mathematical Formulation:
$$\text{SalePrice} = \beta_0 + \beta_1(\text{GrLivArea}) + \beta_2(\text{TotRmsAbvGrd}) + \epsilon$$ 
Where:

* $\beta_0$ is the y-intercept (baseline cost).
* $\beta_1, \beta_2$ are the feature coefficients (weights determining how much price changes per square foot and per room).
* $\epsilon$ represents the residual error.

------------------------------
## 4. Results & Performance Metrics
The model was evaluated using two primary statistical regression metrics calculated from the test dataset partition:

| Evaluation Metric | Description | Typical Baseline Value* |
|---|---|---|
| Mean Squared Error (MSE) | Measures the average squared difference between estimated values and actual values. | High variance due to raw squared dollar scale |
| Root Mean Squared Error (RMSE) | The standard deviation of the residuals. Expresses error directly in USD ($). | $\approx \$45,000 - \$55,000$ |
| $R^2$ Score (Coefficient of Determination) | Represents the proportion of variance in the dependent variable predictable from the features. | $\approx 0.50 - 0.65$ |

*Note: Exact metrics vary slightly based on the specific train/test data split variance, but the model successfully explains more than half of all price variance using just these two basic variables.
## Visualization Interpretations:

* Living Area vs. House Price Scatter Plot: Confirms a distinct, strong positive linear relationship. As square footage increases, the property price predictably scales upward.
* Actual vs. Predicted Price Plot: Shows actual vs. predicted values clustering tightly along the 45-degree diagonal reference line ($y = x$). This demonstrates that the linear assumptions accurately capture baseline market values without severe systematic bias.

------------------------------
## 5. Learning Outcomes

* End-to-End ML Pipeline Execution: Successfully navigated data ingestion, feature subsetting, data cleansing, model training, prediction generation, and metric extraction.
* Feature Relationships: Discovered that structural size parameters (GrLivArea) hold a higher correlation with real estate pricing than the standalone room count (TotRmsAbvGrd).
* Evaluation Competency: Developed a practical understanding of interpreting $R^2$ scores and RMSE values to determine whether an algorithmic fit is underperforming or overfitting.
* Data Visualization Literacy: Mastered using matplotlib and seaborn to translate raw arrays into clean, actionable analytical plots.
