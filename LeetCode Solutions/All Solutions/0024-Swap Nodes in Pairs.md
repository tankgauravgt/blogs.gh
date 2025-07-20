---
title: "0024: Swap Nodes in Pairs"
---
```python
class Solution:
    def swapPairs(self, head):
        
        dummy = ListNode(0, head)
        
        it = dummy
        while it and it.next and it.next.next:
            first = it.next
            second = it.next.next
            
            first.next = second.next
            second.next = first
            it.next = second
            
            it = it.next.next
        
        return dummy.next
```
