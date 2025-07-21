---
title: "0322: Coin Change"
---
```python
class Solution:
    def coinChange(self, coins, amount):
        dp = [1e9] * (1 + amount)
        dp[0] = 0
        for coin in coins:
            for ix in range(coin, 1 + amount, 1):
                dp[ix] = min(dp[ix], 1 + dp[ix - coin])
        return -1 if dp[amount] == 1e9 else dp[amount]
```
