---
title: "0014: Longest Common Prefix"
---
```python
class Solution:
    def longestCommonPrefix(self, strs):
        
        pfx = []
        for t in zip(*strs):
            if len(t) == len(strs) and len(set(t)) == 1:
                pfx.append(t[0])
                continue
            break
        return "".join(pfx)
```
