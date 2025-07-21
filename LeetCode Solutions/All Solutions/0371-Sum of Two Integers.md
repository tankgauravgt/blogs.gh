---
title: "0371: Sum of Two Integers"
---
```python
class Solution:
    def getSum(self, a, b):
        MASK = 0xFFFFFFFF
        acc = a
        bfr = b
        while bfr:
            carry = ((acc & bfr) << 1) & MASK
            sum_without_carry = (acc ^ bfr) & MASK
            acc = sum_without_carry
            bfr = carry
        return acc if acc <= 2 ** 31 - 1 else ~(acc ^ MASK)
```
