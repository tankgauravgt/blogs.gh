---
title: "0056: Merge Intervals"
---
```python
class Solution:
    def merge(self, intervals):
	    
        intervals.sort(key=lambda x: (x[0], x[1]))
        prev = intervals[0]
        
        out = [prev]
        for ix in range(1, len(intervals)):
            curr = intervals[ix]
            if prev[1] >= curr[0]:
                prev[1] = max(prev[1], curr[1])
                continue
            out.append(curr)
            prev = curr
        
        return out
```
