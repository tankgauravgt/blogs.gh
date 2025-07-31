---
title: "0029: Divide Two Integers"
---
```python
class Solution:
    def divide(self, dividend, divisor):
	    
        MIN_VAL, MAX_VAL = -(2 ** 31), +(2 ** 31 - 1)
        
        if dividend == MIN_VAL and divisor == -1:
            return MAX_VAL
        
        sign = -1 if (dividend < 0) ^ (divisor < 0) else +1
        
        dividend = abs(dividend)
        divisor = abs(divisor)
        
        quotient = 0
        for ix in range(31, -1, -1):
            
            subtrahend = (divisor << ix)
            
            if dividend >= subtrahend:
                dividend = dividend - subtrahend
                quotient = quotient + (1 << ix)
        
        return -quotient if sign == -1 else quotient
```
