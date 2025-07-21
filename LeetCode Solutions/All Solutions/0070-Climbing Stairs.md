---
title: "0070: Climbing Stairs"
---
```python
class Solution:
    def climbStairs(self, n):
        def rec(k):
            if k < 2:
                return 1
            return rec(k - 1) + rec(k - 2)
        return rec(n)
```
