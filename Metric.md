# 📊 Model Evaluation Metrics — How to Know If Your Model’s Winning  
> “Because accuracy alone doesn’t tell the whole story.” 😅🔍

---

## 🧮 Linear Regression Metrics  
Used when the target variable is **continuous** (e.g., house price, temperature).

| Metric               | Description                                      | When to Use                                      | When to Avoid                                      | Compatible With               | Formula & Python Function                              |
|----------------------|--------------------------------------------------|--------------------------------------------------|----------------------------------------------------|-------------------------------|--------------------------------------------------------|
| **MAE**              | Mean Absolute Error                              | When you want a simple, interpretable error      | When you need to penalize large errors more        | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( MAE = \frac{1}{n} \sum |y_i - \hat{y}_i| \) <br> `mean_absolute_error()` |
| **MSE**              | Mean Squared Error                               | When large errors should be penalized heavily    | When outliers dominate and distort the average     | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( MSE = \frac{1}{n} \sum (y_i - \hat{y}_i)^2 \) <br> `mean_squared_error()` |
| **RMSE**             | Root Mean Squared Error                          | When interpretability in original units matters  | When outliers skew the error too much              | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( RMSE = \sqrt{MSE} \) <br> `mean_squared_error()` + `np.sqrt()` |
| **R² Score**         | Proportion of variance explained                 | When assessing overall fit of the model          | When comparing models with different feature sets  | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( R^2 = 1 - \frac{SS_{res}}{SS_{tot}} \) <br> `r2_score()` |
| **Adjusted R²**      | R² adjusted for number of predictors             | When comparing models with different complexities| When feature count is low or irrelevant            | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( R^2_{adj} = 1 - \frac{(1 - R^2)(n - 1)}{n - p - 1} \) <br> Manual calc |
| **MAPE**             | Mean Absolute Percentage Error                   | When relative error matters (e.g., forecasting)  | When target values are near zero                   | ✅ Ridge, ✅ Lasso, ⚠️ Baseline | \( MAPE = \frac{100}{n} \sum \left| \frac{y_i - \hat{y}_i}{y_i} \right| \) <br> `mean_absolute_percentage_error()` |
| **Explained Variance**| Measures proportion of variance explained       | When you want a smoother alternative to R²       | When exact fit diagnostics are needed              | ✅ Ridge, ✅ Lasso, ✅ Baseline | \( EV = 1 - \frac{Var(y - \hat{y})}{Var(y)} \) <br> `explained_variance_score()` |


### 📌 Python Snippet: MAE, MSE, R²

```python
import numpy as np
from sklearn.metrics import (
    mean_absolute_error,
    mean_squared_error,
    r2_score,
    mean_absolute_percentage_error,
    explained_variance_score
)

# Sample data
y_true = [3, 5, 2.5, 7]
y_pred = [2.8, 5.1, 2.7, 6.8]

# Core metrics
mae = mean_absolute_error(y_true, y_pred)
mse = mean_squared_error(y_true, y_pred)
rmse = np.sqrt(mse)
r2 = r2_score(y_true, y_pred)
mape = mean_absolute_percentage_error(y_true, y_pred)
explained_var = explained_variance_score(y_true, y_pred)

# Adjusted R² (manual calculation)
n = len(y_true)         # number of samples
p = 1                   # number of predictors (set appropriately)
adj_r2 = 1 - (1 - r2) * (n - 1) / (n - p - 1)

# Display results
print("MAE:", mae)
print("MSE:", mse)
print("RMSE:", rmse)
print("R²:", r2)
print("Adjusted R²:", adj_r2)
print("MAPE:", mape)
print("Explained Variance:", explained_var)
```



