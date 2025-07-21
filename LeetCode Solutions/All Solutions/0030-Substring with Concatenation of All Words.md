---
title: "0030: Substring with Concatenation of All Words"
---
```python
from collections import Counter

class Solution:
    def findSubstring(self, s, words):
        N = len(words)
        L = len(words[0])
        if len(s) < N * L:
            return []
        
        target = Counter(words)
        def check(s, sid, tgt, N, L):
            sx = sid
            buf = []
            while sx < sid + N * L:
                buf.append(s[sx:sx + L])
                sx = sx + L
            return Counter(buf) == tgt
        
        results = []
        tgt_hash_val = sum([sum(map(ord, word)) for word in words])
        src_hash_val = sum(map(ord, s[0:N * L]))
        for ix in range(len(s) - N * L + 1):
            if ix != 0:
                src_hash_val = src_hash_val - ord(s[ix - 1])
                src_hash_val = src_hash_val + ord(s[ix + N * L - 1])
            if src_hash_val != tgt_hash_val: continue
            if check(s, ix, target, N, L):
                results.append(ix)
        
        return results
```
