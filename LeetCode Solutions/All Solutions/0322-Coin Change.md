---
title: "0322: Coin Change"
---
```python
class Solution:
    def coinChange(self, coins, amount):
        
        @cache
        def rec(n):
            if n >= amount:
                return 0 if (n == amount) else float('inf')
            cmin = float('inf')
            for coin in coins:
                cmin = min(cmin, 1 + rec(n + coin))
            return cmin
        
        out = rec(0)
        return out if out != float('inf') else -1
```
