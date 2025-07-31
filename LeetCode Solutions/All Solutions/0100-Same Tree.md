---
title: "0100: Same Tree"
---
```python
class Solution:
    def isSameTree(self, p, q):
        def rec(n1, n2):
            if not n1 and not n2: return True
            if n1 and not n2: return False
            if n2 and not n1: return False
            return n1.val == n2.val and rec(n1.left, n2.left) and rec(n1.right, n2.right)
        return rec(p, q)
```
