---
title: "0006: Zigzag Conversion"
---
```python
class Solution:
    def convert(self, s, numRows):
        if numRows == 1: return s
        out = [[] for ix in range(numRows)]
        px = 0
        reverse = True
        for cx, c in enumerate(s):
            if px == 0 or px == numRows - 1:
                reverse = not reverse
            out[px].append(c)
            px = px + (1 if not reverse else -1)
        
        return "".join(["".join(o) for o in out])
```
