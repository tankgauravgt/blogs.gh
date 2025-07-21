---
title: "0190: Reverse Bits"
---
```python
class Solution:
    def reverseBits(self, n):
        bits = []
        while n:
            bits.append(n % 2)
            n = n // 2
        while len(bits) < 32:
            bits.append(0)
        count = 0
        for n in bits:
            count = 2 * count + n
        return count
```
