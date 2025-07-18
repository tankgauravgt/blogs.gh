---
title: "0012: Integer to Roman"
---
```python
class Solution:
    def intToRoman(self, num):
        
        keys = [
	        1000, 900, 500, 400, 100, 
	        90, 50, 40, 10, 9, 5, 4, 1
	    ]
        vals = [
	        'M', 'CM', 'D', 'CD', 'C', 
	        'XC', 'L', 'XL', 'X', 'IX', 
	        'V', 'IV', 'I'
	    ]
	    
        cache = dict(zip(keys, vals))
        
        ix = 0
        out = []
        while num:
            while num < keys[ix]:
                ix = ix + 1
            num = num - keys[ix]
            out.append(vals[ix])
        return "".join(out)
```
