---
title: "0008: String to Integer (atoi)"
---
```python
class Solution:
    def myAtoi(self, s):
    
        skipWhiteSpace = True
        parseNumberSign = True
        skipInitZeros = True
        
        sign = '+'
        out = []
        for ix, c in enumerate(s):
            
            if skipWhiteSpace and c == ' ':
                continue
            skipWhiteSpace = False
            
            if parseNumberSign and c in '+-':
                parseNumberSign = False
                sign = c
                continue
            parseNumberSign = False
            
            if c in '+-':
                break
            
            if skipInitZeros and c == '0':
                continue
            skipInitZeros = False
            
            if c not in '0123456789':
                break
            
            out.append(c)
            
        if not out: return 0
        
        out = int("".join(out)) * (-1 if sign == '-' else +1)
        out = -(2 ** 31) if out <= -(2 ** 31) else out
        out = (2 ** 31 - 1) if out >= (2 ** 31 - 1) else out
        return out
```
