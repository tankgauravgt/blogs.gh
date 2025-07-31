---
title: "0014: Longest Common Prefix"
---
```python
class Solution:
    def longestCommonPrefix(self, strs):
        smin = min(strs, key=len)
        for ix, c in enumerate(smin):
            if len(set([s[ix] for s in strs])) != 1:
                return smin[:ix]
        return smin
```
