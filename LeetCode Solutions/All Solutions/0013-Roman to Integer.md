---
title: "0013: Roman to Integer"
---
```python
class Solution:
    def romanToInt(self, s):
    
        valmap = {
            'I': 1, 
            'IV': 4, 
            'V': 5, 
            'IX': 9, 
            'X': 10, 
            'XL': 40,
            'L': 50,
            'XC': 90,
            'C': 100,
            'CD': 400,
            'D': 500,
            'CM': 900,
            'M': 1000
        }
        
        lx = 0
        total = 0
        while lx < len(s):
            found_prefix = False
            # two char prefix:
            for pre in ['CM', 'CD', 'XC', 'XL', 'IX', 'IV']:
                if s[lx::].startswith(pre):
                    total = total + valmap[pre]
                    lx = lx + len(pre)
                    found_prefix = True
                    break
            # one char prefix:
            if not found_prefix and lx < len(s):
                total = total + valmap[s[lx]]
                lx = lx + 1
        return total
```
