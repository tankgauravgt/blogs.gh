---
title: "0011: Container With Most Water"
---
```python
class Solution:
    def maxArea(self, height):
        
        N = len(height)
        
        lx, rx = 0, N - 1
        
        cmax = 0
        while lx < rx:
            if height[lx] <= height[rx]:
                minH = min(height[lx], height[rx])
                cmax = max(cmax, minH * (rx - lx))
                lx = lx + 1
            else:
                minH = min(height[lx], height[rx])
                cmax = max(cmax, minH * (rx - lx))
                rx = rx - 1
        return cmax
```
