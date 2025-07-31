---
title: "0190: Reverse Bits"
---
```python
class Solution:
    def reverseBits(self, n: int) -> int:
        out = 0
        for ix in range(31, -1, -1):
            out = (out << 1) | (n & 1)
            n = n >> 1
        return out
```
