---
title: "0424: Longest Repeating Character Replacement"
---
```python
class Solution:
    def characterReplacement(self, s, k):
        lx = 0
        maxf = 0
        cmax = 0
        cache = {}
        for rx, c in enumerate(s):
            cache[c] = cache.get(c, 0) + 1
            maxf = max(maxf, cache[c])
            while (rx - lx + 1) - maxf > k:
                cache[s[lx]] = cache[s[lx]] - 1
                lx = lx + 1
            cmax = max(cmax, rx - lx + 1)
        return cmax
```
