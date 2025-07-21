---
title: "0048: Rotate Image"
---
```python
class Solution:
    def rotate(self, matrix):
        matrix.reverse()
        N = len(matrix)
        for rx in range(N):
            for cx in range(0, 1 + rx):
                matrix[rx][cx], matrix[cx][rx] = matrix[cx][rx], matrix[rx][cx]
```
