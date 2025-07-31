---
title: "0152: Maximum Product Subarray"
---
```python
class Solution:
    def maxProduct(self, nums):
        out = cmin = cmax = nums[0]
        
        for n in nums[1:]:
            candidates = (n, cmin * n, cmax * n)
            cmax = max(candidates)
            cmin = min(candidates)
            out = max(out, cmax)
        
        return out
```
