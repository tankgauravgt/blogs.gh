---
title: "0295: Find Median from Data Stream"
---
```python
import heapq

class MedianFinder:
    def __init__(self):
        self.minheap = []
        self.maxheap = []
        
    def addNum(self, num):
        if (not self.maxheap) or (-self.maxheap[0] >= num):
            heapq.heappush(self.maxheap, -num)
        else:
            heapq.heappush(self.minheap, num)
        
        if len(self.maxheap) < len(self.minheap):
            heapq.heappush(self.maxheap, -heapq.heappop(self.minheap))
        if len(self.maxheap) - 1 > len(self.minheap):
            heapq.heappush(self.minheap, -heapq.heappop(self.maxheap))
                
    def findMedian(self):
        if len(self.minheap) == len(self.maxheap):
            return (self.minheap[0] - self.maxheap[0]) / 2
        return -self.maxheap[0]
```
