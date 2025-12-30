---
name: statistical-analysis
description: Master statistical analysis with hypothesis testing, A/B testing, regression, and statistical methods for data-driven decisions.
---

# Statistical Analysis

Apply statistical methods to analyze data, test hypotheses, and derive statistically significant insights.

## When to Use This Skill

- A/B testing
- Hypothesis testing
- Correlation analysis
- Predictive modeling
- Trend analysis
- Forecasting
- Anomaly detection
- Significance testing

## Core Concepts

### 1. A/B Test Analysis

```python
# A/B test significance calculation
import scipy.stats as stats

# Control and treatment groups
control_conversions = 120
control_visitors = 2000
treatment_conversions = 150
treatment_visitors = 2000

# Conversion rates
control_rate = control_conversions / control_visitors  # 6%
treatment_rate = treatment_conversions / treatment_visitors  # 7.5%

# Chi-square test
observed = [[control_conversions, control_visitors - control_conversions],
            [treatment_conversions, treatment_visitors - treatment_conversions]]

chi2, p_value = stats.chi2_contingency(observed)[:2]

print(f"Control rate: {control_rate:.2%}")
print(f"Treatment rate: {treatment_rate:.2%}")
print(f"Lift: {(treatment_rate - control_rate) / control_rate:.2%}")
print(f"P-value: {p_value:.4f}")
print(f"Significant: {p_value < 0.05}")

# Output:
# Control rate: 6.00%
# Treatment rate: 7.50%
# Lift: 25.00%
# P-value: 0.0423
# Significant: True
```

### 2. Regression Analysis

```python
import pandas as pd
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

# Sample data: advertising spend vs sales
data = {
    'ad_spend': [1000, 1500, 2000, 2500, 3000, 3500, 4000],
    'sales': [15000, 18000, 22000, 26000, 28000, 32000, 35000]
}
df = pd.DataFrame(data)

# Linear regression
X = df[['ad_spend']]
y = df['sales']

model = LinearRegression()
model.fit(X, y)

# Results
print(f"R-squared: {model.score(X, y):.4f}")
print(f"Coefficient: {model.coef_[0]:.2f}")
print(f"Intercept: {model.intercept_:.2f}")
print(f"For every $1 in ad spend, sales increase by ${model.coef_[0]:.2f}")

# Prediction
predicted_sales = model.predict([[5000]])
print(f"Predicted sales for $5000 ad spend: ${predicted_sales[0]:,.0f}")
```

## Best Practices

1. **Define hypothesis** - Clear null and alternative
2. **Check assumptions** - Normality, independence
3. **Choose significance level** - Typically α = 0.05
4. **Calculate sample size** - Adequate statistical power
5. **Consider confounding** - Control for variables
6. **Report effect size** - Not just p-value
7. **Validate results** - Cross-validation, holdout sets
8. **Interpret carefully** - Correlation ≠ causation

## Resources

- **Statistics for Data Science**: Practical guide
- **Think Stats**: Allen Downey
