---
title: "0022: Generate Parenthesis"
---
```python
class Solution:
    def generateParenthesis(self, n):
	    
        def generate(ob, cb, buf, output):
            if cb > ob:
                return
            if len(buf) == 2 * n:
                output.append("".join(buf))
                return
            if ob < n:
                buf.append('(')
                generate(ob + 1, cb, buf, output)
                buf.pop()
            buf.append(')')
            generate(ob, cb + 1, buf, output)
            buf.pop()
        
        result = []
        generate(0, 0, [], result)
        return result
```
