---
title: "0347: Top K Frequent Elements"
---
```python
from collections import Counter

class Solution:
    def topKFrequent(self, nums, k):
        freq = Counter(nums)
        topk = sorted([(v, k) for k, v in freq.items()])[-k::]
        return list(map(lambda x: x[1], topk))
```
