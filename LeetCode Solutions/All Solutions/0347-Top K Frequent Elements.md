---
title: "0347: Top K Frequent Elements"
---
```python
from collections import Counter

class Solution:
    def topKFrequent(self, nums, k):
        
        freq = Counter(nums)
        buckets = [[] for _ in range(len(nums) + 1)]
        
        for num, count in freq.items():
            buckets[count].append(num)
        
        res = []
        for i in range(len(buckets) - 1, 0, -1):
            for num in buckets[i]:
                res.append(num)
                if len(res) == k:
                    return res
```