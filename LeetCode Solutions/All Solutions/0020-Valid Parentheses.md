---
title: "0020: Valid Parentheses"
---
```python
class Solution:
    def isValid(self, s):        
        stk = []
        for cx, c in enumerate(s):
            if c in '[{(':
                stk.append(c)
                continue
            if c == ')' and stk and stk[-1] == '(':
                stk.pop()
                continue
            if c == ']' and stk and stk[-1] == '[':
                stk.pop()
                continue
            if c == '}' and stk and stk[-1] == '{':
                stk.pop()
                continue
            return False
        return len(stk) == 0
```
