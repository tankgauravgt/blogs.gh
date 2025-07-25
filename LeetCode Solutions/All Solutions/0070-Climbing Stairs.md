---
title: "0070: Climbing Stairs"
---
```python
from functools import lru_cache

class Solution:
    def climbStairs(self, n):
		
		@lru_cache(maxsize=None)
        def rec(k):
            if k < 2:
                return 1
            return rec(k - 1) + rec(k - 2)
        
        return rec(n)
```
