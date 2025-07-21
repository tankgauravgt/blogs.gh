---
title: "0055: Jump Game"
---
```python
class Solution:
    def canJump(self, nums):
        if len(nums) == 1: return True
        cmax = 0
        for ix, n in enumerate(nums):
            if cmax >= ix:
                cmax = max(cmax, ix + n)
        return cmax >= len(nums) - 1
```
