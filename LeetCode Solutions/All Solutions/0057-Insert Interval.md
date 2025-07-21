---
title: "0057: Insert Interval"
---
```python
class Solution:
    def insert(self, intervals, newInterval):
	    
        intervals.append(newInterval)
        intervals.sort(key=lambda x: (x[0], x[1]))
        
        prev = intervals[0]
        
        out = [prev]
        N = len(intervals)
        for ix in range(1, N):
            curr = intervals[ix]
            if prev[1] >= curr[0]:
                prev[1] = max(prev[1], curr[1])
                continue
            out.append(curr)
            prev = curr
        
        return out
```