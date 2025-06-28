---
## Goal?

{text}

---
## Loss Function

{text}


---
## Objective

{text}


---
## Applications

{list}

# Logistic Regression

Logistic regression models the probability of a binary outcome $y \in \{0,1\}$ given features $X$:

$$
P(y=1|X) = \sigma(X\beta) = \frac{1}{1 + e^{-X\beta}}
$$

The log-likelihood is maximized to estimate $\beta$:

$$
\ell(\beta) = \sum_{i=1}^n \left[y_i \log \sigma(X_i\beta) + (1-y_i) \log (1-\sigma(X_i\beta))\right]
$$

Assumptions: independence, linearity in log-odds, no multicollinearity.

---

- Prediction: $\hat{y} = 1$ if $P(y=1|X) > 0.5$
- Loss: Binary cross-entropy