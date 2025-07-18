---
title: "0025: Reverse Nodes in k-Group"
---
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseKGroup(self, head, k):
        def revk(node, k):
            prev, curr = None, node
            while k > 0 and curr:
                k, prev, curr.next, curr = k - 1, curr, prev, curr.next
            return prev, curr, k == 0
            
        result = ListNode(-1)
        
        curr = head
        rptr = result
        while curr:
            done, curr, success = revk(curr, k)
            while rptr and rptr.next: rptr = rptr.next
            rptr.next = done if success else revk(done, k)[0]
        return result.next

```
