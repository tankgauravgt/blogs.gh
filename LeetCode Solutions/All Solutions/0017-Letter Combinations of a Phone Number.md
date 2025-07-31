---
title: "0017: Letter Combinations of a Phone Number"
---
```python
class Solution:
    def letterCombinations(self, digits):
        
        cmap = {
            '2': 'abc',
            '3': 'def',
            '4': 'ghi',
            '5': 'jkl',
            '6': 'mno',
            '7': 'pqrs',
            '8': 'tuv',
            '9': 'wxyz'
        }
        
        def btrack(ix, buf, res):
            if ix == len(digits):
                if buf:
                    res.append("".join(buf))
                return
            for c in cmap[digits[ix]]:
                buf.append(c)
                btrack(ix + 1, buf, res)
                buf.pop()
                
        result = []
        btrack(0, [], result)
        return result
```
