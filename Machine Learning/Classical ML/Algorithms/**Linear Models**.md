---
title: Linear Models
---
Target value $\hat{y}$ is expected to be a linear combination of the features $X$.

Mathematically,

$$
\hat{y} = \mathbf{w_{0}} + \sum_{d=1}^{D} \mathbf{w_{d}} x_{d}
$$

---
## **1. Ordinary Least Squares**

### **1.1. Assumptions**

1. The target value is a linear combination of the features.
2. Features are independent.
3. The design matrix is not close to singular (no multicollinearity).

### **1.2. Objective function**
$$\mathbf{w}_{*} = \underset{ \mathbf{w} }{\operatorname{arg max}}\ \Bigg\|\ X\mathbf{w} - y \ \Bigg\|_{2}^2$$
### **1.3. Code Example**

```python
from sklearn.linear_model import LinearRegression

inputs = np.random.rand(10, 3)
labels = np.random.rand(10, 1)

model = LinearRegression()

model.fit(inputs, labels)
```


### **1.4. Variants**

#### **1.4.1. Ordinary Non-Negative Least Squares**

Sometimes you don't want the weights to be negative. I.e., when estimating positive quantities like price of goods.

```python
model = linear_model.LinearRegression(positive=True)
```

---
