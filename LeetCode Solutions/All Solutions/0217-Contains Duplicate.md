---
title: "0217: Contains Duplicate"
---
```python
class Solution:
    def containsDuplicate(self, nums):
        cache = set()
        for n in nums:
            if n in cache:
                return True
            cache.add(n)
        return False
```
