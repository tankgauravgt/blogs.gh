Target value $\hat{y}$ is expected to be a linear combination of the features $X$.

```python
from sklearn.linear_model import LinearRegression

# +-------------+
# inputs: [N, D]
# labels: [N, 1]
# +-------------+

# create linear model
model = linear_model.LinearRegression()

# fit model on data
model.fit(inputs, labels)
```

## 1. Ordinary Least Squares

$$\mathbf{w}, b = \underset{\mathbf{w},b}{\operatorname{arg max}} \bigg\| (X\mathbf{w} + b) - y \bigg\|_{2}^2$$
$\underset{}{}$
