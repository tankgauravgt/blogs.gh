---
title: "0242: Valid Anagram"
---
```python
from collections import Counter

class Solution:
    def isAnagram(self, s, t):
        if len(s) != len(t):
            return False
        return Counter(s) == Counter(t)
```