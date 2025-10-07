# 🧪 Linear Regression Diagnostics — Residuals, Linearity & Normality  
> “Because a good fit isn’t just about R²—it’s about what the errors whisper.” 😅📉

---

<details>
<summary>📍 1. Residual Analysis</summary>

Residuals are the differences between actual and predicted values:



\[
\text{Residual}_i = y_i - \hat{y}_i
\]



### ✅ What to Look For:
- Random scatter (no pattern)
- Constant variance (homoscedasticity)
- No autocorrelation

📊 **Plot**: Residuals vs Fitted Values  
Helps detect non-linearity or heteroscedasticity.

</details>

---

<details>
<summary>📈 2. Linearity Check</summary>

We assume a **linear relationship** between predictors and target.

### ✅ What to Look For:
- Points hugging the diagonal line
- No curvature or funnel shapes

📊 **Plot**: Observed vs Predicted Values  
Confirms if predictions scale linearly with actuals.

</details>

---

<details>
<summary>📉 3. Residuals vs Fitted Plot</summary>

This plot shows residuals on the y-axis and fitted values on the x-axis.

### ✅ What to Look For:
- Horizontal band around zero
- No systematic patterns

📊 **Plot**: Residuals vs Fitted  
Detects non-linearity, outliers, and variance issues.

</details>

---

<details>
<summary>📐 4. Normality of Residuals</summary>

Linear regression assumes residuals are **normally distributed**.

### ✅ What to Look For:
- Bell-shaped histogram
- Q-Q plot points on diagonal

📊 **Plots**:
- Histogram of Residuals  
- Q-Q Plot of Residuals

</details>

### 📷 Linear Regression Diagnostic Checks  
> Visualizing residual behavior, linearity, and normality assumptions

<table>
  <tr>
    <td align="center"><strong>Linearity Check</strong><br>
      <img src="https://github.com/SuyashNagarGT/MachineLearning/raw/main/Lin_Checks.png" width="400"/>
    </td>
    <td align="center"><strong>Residuals vs Fitted</strong><br>
      <img src="https://github.com/SuyashNagarGT/MachineLearning/blob/b5b2cc72af8a87e23fa046d63ae76e33c34f5579/res_fitted.png" width="400"/>
    </td>
  </tr>
  <tr>
    <td align="center"><strong>Q-Q Plot</strong><br>
      <img src="https://github.com/SuyashNagarGT/MachineLearning/blob/b5b2cc72af8a87e23fa046d63ae76e33c34f5579/QQ.png" width="400"/>
    </td>
    <td align="center"><strong>Histogram of Residuals</strong><br>
      <img src="https://github.com/SuyashNagarGT/MachineLearning/blob/b5b2cc72af8a87e23fa046d63ae76e33c34f5579/hist_res.png" width="400"/>
    </td>
  </tr>
</table>



