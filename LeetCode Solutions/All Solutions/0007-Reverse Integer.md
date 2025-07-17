---
title: "0007: Reverse Integer"
---
```python
class Solution:
    def reverse(self, x):
    
        if x == 0: return 0
        
        while x % 10 == 0:
            x = x // 10
        
        neg = x < 0
        
        x = abs(x)
        
        res = 0
        while x:
            res = res * 10
            res = res + (x % 10)
            x = x // 10
        
        out = res if not neg else -res
        return out if out in range(-(2**31), (2**31)) else 0
```
