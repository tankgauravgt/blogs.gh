---
title: "0152: Maximum Product Subarray"
---
```python
class Solution:
    def maxProduct(self, nums):
        answer = max(nums)
        cmin, cmax = 1, 1
        for n in nums:
            if n == 0:
                cmin, cmax = 1, 1
                continue
            p1, p2 = cmax * n, cmin * n
            cmax = max(p1, p2, n)
            cmin = min(p1, p2, n)
            answer = max(answer, cmax)
        return answer
```
