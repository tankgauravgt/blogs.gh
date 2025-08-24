---
title: "0271: Encode and Decode Strings"
tags:
  - Array
  - String
  - Design
---
### Problem Statement

### Code Solution

```python
class Solution:
    def encode(self, strs):
        out = []
        for sx, s in enumerate(strs):
            N = len(s)
            out.append(f"{N}#{s}")
        return "".join(out)
    
    def decode(self, s):
        out = []
        while s:
            ix = s.find('#')
            clen, cstr = int(s[:ix]), s[1 + ix:]
            out.append(cstr[0:clen])
            s = cstr[clen::]
        return out
```
