---
title: "0049: Group Anagrams"
---
```python
class Solution:
    def groupAnagrams(self, strs):
        cache = {}
        for sx, s in enumerate(strs):
            temp = "".join(sorted(s))
            if temp not in cache:
                cache[temp] = []
            cache[temp].append(s)
        return [v for k, v in cache.items()]
```
