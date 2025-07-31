---
title: "0019: Remove Nth Node From End of List"
---
```python
class Solution:
    def removeNthFromEnd(self, head, n):
        temp = head
        for ix in range(n):
            temp = temp.next
        
        if not temp:
            return head.next
        
        curr = head
        while temp and temp.next:
            curr = curr.next
            temp = temp.next
        
        curr.next = curr.next.next
        return head
```
