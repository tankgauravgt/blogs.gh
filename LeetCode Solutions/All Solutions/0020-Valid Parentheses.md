---
title: "0020: Valid Parentheses"
---
```python
class Solution:
    def isValid(self, s):
        
        count = []
        for cx, c in enumerate(s):
            if c in '()':
                if c == '(' or not count: count.append(c)
                if c == ')' and count and count[-1] != '(': count.append(c)
                if c == ')' and count and count[-1] == '(': count.pop()
            if c in '[]':
                if c == '[' or not count: count.append(c)
                if c == ']' and count and count[-1] != '[': count.append(c)
                if c == ']' and count and count[-1] == '[': count.pop()
            if c in '{}':
                if c == '{' or not count: count.append(c)
                if c == '}' and count and count[-1] != '{': count.append(c)
                if c == '}' and count and count[-1] == '{': count.pop()
        
        return len(count) == 0
```
