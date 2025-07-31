---
title: "0191: Number of 1 Bits"
---
```python
class Solution:
    def hammingWeight(self, n):
        count = 0
        while n:
            count += n % 2
            n //= 2
        return count
```
