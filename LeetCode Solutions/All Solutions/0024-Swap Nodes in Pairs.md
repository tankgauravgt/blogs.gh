---
title: "0024: Swap Nodes in Pairs"
---
```python
class Solution:
    def swapPairs(self, head):
        
        dummy = ListNode(-1, head)
        
        prev = dummy
        while prev and prev.next and prev.next.next:
            first = prev.next
            second = prev.next.next
            
            first.next = second.next
            second.next = first
            prev.next = second
            
            prev = first
        
        return dummy.next
```
