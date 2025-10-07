# 🧠 Regularization — When Your Model Needs a Reality Check  
> “Because memorizing the training data isn’t the same as learning from it.” 😅📉

Regularization adds a **penalty** to your model’s loss function to discourage complexity and prevent overfitting. It’s like telling your model:  
_“Stop obsessing over every detail. Focus on the big picture.”_

---

<details>
<summary>📚 What Is Regularization?</summary>

Regularization modifies the loss function:

Loss
=
Error
+
𝜆
∑
𝑤
𝑖


\[
\text{Loss} = \text{Error} + \lambda \times \text{Penalty}
\]



Where:  
- **Error** = how far predictions are from actual values  
- **Penalty** = complexity cost (based on coefficients)  
- \( \lambda \) = regularization strength

The higher the penalty, the more the model is nudged toward simplicity.

</details>

---

<details>
<summary>🔍 Types of Regularization</summary>

### 🧹 Ridge Regression (L2 Regularization)  
> _“I won’t eliminate your quirks, but I’ll tone them down.”_

- Adds **squared magnitude** of coefficients  
- Shrinks coefficients but doesn’t eliminate them  
- Great for **multicollinearity**



\[
\text{Loss} = \text{Error} + \lambda \sum w_i^2
\]



---

### ✂️ Lasso Regression (L1 Regularization)  
> _“If you’re not useful, you’re out.”_

- Adds **absolute value** of coefficients  
- Can shrink some coefficients to **zero**  
- Helps with **feature selection**



\[
\text{Loss} = \text{Error} + \lambda \sum |w_i|
\]



---

### 🧪 Elastic Net  
> _“Let’s blend the best of both worlds.”_

- Combines **L1 and L2 penalties**  
- Balances shrinkage and selection  
- Useful when features are **correlated**



\[
\text{Loss} = \text{Error} + \lambda_1 \sum |w_i| + \lambda_2 \sum w_i^2
\]



</details>

---

<details>
<summary>📊 Click to copy Python snippet for Lasso Regression</summary>

```python
from sklearn.linear_model import Lasso
from sklearn.datasets import make_regression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# Generate sample data
X, y = make_regression(n_samples=100, n_features=5, noise=0.1, random_state=42)

# Split into train/test
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Apply Lasso
lasso = Lasso(alpha=0.1)
lasso.fit(X_train, y_train)

# Evaluate
y_pred = lasso.predict(X_test)
print("MSE:", mean_squared_error(y_test, y_pred))
print("Coefficients:", lasso.coef_)
