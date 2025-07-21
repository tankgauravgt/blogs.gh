---
title: "1143: Longest Common Subsequence"
---
```python
from functools import lru_cache

class Solution:
    def longestCommonSubsequence(self, text1, text2):
        @lru_cache(maxsize=None)
        def lcs(t1, t2):
            if t1 >= len(text1):
                return 0
            if t2 >= len(text2):
                return 0
            if text1[t1] == text2[t2]:
                return 1 + lcs(1 + t1, 1 + t2)
            else:
                return max(
                    lcs(1 + t1, t2),
                    lcs(t1, 1 + t2)
                )
        return lcs(0, 0)
```
