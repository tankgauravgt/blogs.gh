---
title: "0070: Climbing Stairs"
---
```python
from functools import lru_cache

class Solution:
    def climbStairs(self, n):
		
		@cache
        def rec(k):
            if k >= n:
                return 0
            takeit = rec(k + 1)
            skipit = rec(k + 2)
            return 1 + takeit + skipit
        
        return rec(n)
```
