---
title: "0121: Best Time to Buy and Sell Stock"
---
```python
class Solution:
    def maxProfit(self, prices):
        maxp = 0
        cmin = float('inf')
        for p in prices:
            maxp = max(maxp, p - cmin)
            cmin = min(cmin, p)
        return maxp
```
