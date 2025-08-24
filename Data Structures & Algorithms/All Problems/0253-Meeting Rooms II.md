---
title: "0253: Meeting Rooms II"
tags:
  - Array
  - TwoPointers
  - Greedy
  - Sorting
  - Heap(PriorityQueue)
  - PrefixSum
---
### Problem Statement

### Code Solution

```python
import heapq

class Solution:
    def minMeetingRooms(self, intervals):
	    
        intervals.sort(key=lambda x: (x.start, x.end))
        
        hq = []
        cmax = 0
        for ix, curr in enumerate(intervals):
            while hq and hq[0][0] <= curr.start:
                heapq.heappop(hq)
            heapq.heappush(hq, (curr.end, curr.start))
            cmax = max(cmax, len(hq))
        return cmax
```
