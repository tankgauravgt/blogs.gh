---
title: "0029: Divide Two Integers"
---
```python
class Solution:
    def divide(self, dividend, divisor):
        
        neg = (dividend < 0) ^ (divisor < 0)
        dividend = abs(dividend)
        divisor = abs(divisor)
        
        if divisor == dividend:
            return 1 if not neg else -1
        if divisor == 1:
            dividend = dividend if not neg else -dividend
            return max(-(2 ** 31), min(2 ** 31 - 1, dividend))
            
        count = 0
        while dividend >= divisor:
            ix = 0
            while dividend >= divisor ** (1 + ix):
                ix = ix + 1
            dividend = dividend - (divisor ** ix)
            count = count + (divisor ** (ix - 1))
        
        count = count if not neg else -count
        return max(-(2 ** 31), min(2 ** 31 - 1, count))
```
