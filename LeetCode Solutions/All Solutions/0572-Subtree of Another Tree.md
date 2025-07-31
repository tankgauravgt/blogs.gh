---
title: "0572: Subtree of Another Tree"
---
```python
class Solution:
    def isSubtree(self, root, subRoot):
        def rec(src, tgt):
            if src and tgt:
                if rec(src.left, tgt):
                    return True
                if rec(src.right, tgt):
                    return True
                return src.val == tgt.val and rec(src.left, tgt.left) and rec(src.right, tgt.right)
            return src == tgt
            
        return rec(root, subRoot)
```
