---
title: "0022: Generate Parenthesis"
---
```python
class Solution:
    def generateParenthesis(self, n):
        def rec(k, o, c, buf, res):
            if o > k:
                return
            if c - o > 0:
                return
            if c == o and len(buf) == 2 * k:
                res.append("".join(buf))
                return
            buf.append('(')
            rec(k, 1 + o, c, buf, res)
            buf.pop()
            buf.append(')')
            rec(k, o, 1 + c, buf, res)
            buf.pop()
        res = []
        rec(n, 0, 0, [], res)
        return res
```
