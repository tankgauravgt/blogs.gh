---
title: "0435: Non-overlapping Intervals"
---
```python
class Solution:
    def eraseOverlapIntervals(self, intervals):
        
        intervals.sort(key=lambda x: (x[1], x[0]))
        
        count = 0
        prev = intervals[0]
        for ix in range(1, len(intervals)):
            curr = intervals[ix]
            if prev[1] > curr[0]:
                count = count + 1
                continue
            prev = curr
        
        return count
```
