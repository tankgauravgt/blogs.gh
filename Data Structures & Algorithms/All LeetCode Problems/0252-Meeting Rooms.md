---
title: "0252: Meeting Rooms"
tags:
  - Array
  - Sorting
---
### Problem Statement

### Code Solution

```python
class Solution:
    def canAttendMeetings(self, intervals):
	    
        intervals.sort(key=lambda x: (x.start, x.end))
        
        prev = intervals[0]
        
        N = len(intervals)
        for ix in range(1, N):
            curr = intervals[ix]
            if prev.end > curr.start:
                return False
            prev = curr
        
        return True
```
