---
title: "0338: Counting Bits"
---
```python
class Solution:
    def countBits(self, n):
        counts = []
        for ix in range(1 + n):
            count = 0
            while ix:
                count += ix % 2
                ix //= 2
            counts.append(count)
        return counts
```
