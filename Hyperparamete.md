# 🧠 Parameters vs Hyperparameters — Who Does What in a Model  
> “One learns from data. The other sets the rules of learning.” 😅📊

---

<details>
<summary>📚 What Are Parameters?</summary>

Parameters are **learned from data** during training. They define the model’s internal structure and directly influence predictions.

### 🔧 Examples:
- Coefficients in Linear Regression  
- Weights and biases in Neural Networks  
- Split thresholds in Decision Trees

### 🧠 Key Traits:
- Learned automatically during training  
- Optimized via algorithms like Gradient Descent  
- Cannot be manually set by the user

</details>

---

<details>
<summary>⚙️ What Are Hyperparameters?</summary>

Hyperparameters are **external settings** defined before training. They control the learning process and model behavior.

### 🔍 Examples:
- Learning rate  
- Number of epochs  
- Regularization strength (alpha in Ridge/Lasso)  
- Batch size  
- Number of hidden layers in Neural Networks

### 🧠 Key Traits:
- Set manually by the practitioner  
- Tuned using techniques like Grid Search or Random Search  
- Not learned from data

</details>

---

<details>
<summary>📊 Python Snippet: Hyperparameter in Lasso Regression</summary>

```python
from sklearn.linear_model import Lasso
from sklearn.datasets import make_regression

# Generate sample data
X, y = make_regression(n_samples=100, n_features=5, noise=0.1, random_state=42)

# Lasso with alpha as a hyperparameter
model = Lasso(alpha=0.5)  # alpha is a hyperparameter
model.fit(X, y)

print("Learned Parameters (Coefficients):", model.coef_)
```

---

</details>
<summary>📊 Python Snippet: Hyperparameter in Ridge Regression</summary>
<details>
  

  ```python
from sklearn.linear_model import Ridge
from sklearn.datasets import make_regression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# Generate synthetic regression data
X, y = make_regression(n_samples=100, n_features=5, noise=0.1, random_state=42)

# Split into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Apply Ridge Regression with alpha as a hyperparameter
ridge = Ridge(alpha=1.0)  # alpha controls regularization strength
ridge.fit(X_train, y_train)

# Evaluate the model
y_pred = ridge.predict(X_test)
print("MSE:", mean_squared_error(y_test, y_pred))
print("Learned Coefficients:", ridge.coef_)
```
  
</details>

<details>
<summary>🧪 Summary Table</summary>

| Type           | Learned During Training | Set Before Training | Examples                          |
|----------------|--------------------------|----------------------|-----------------------------------|
| Parameters     | ✅ Yes                   | ❌ No                | Coefficients, weights, biases     |
| Hyperparameters| ❌ No                    | ✅ Yes               | Learning rate, alpha, batch size  |

</details>

