---
title: "0143: Reorder List"
---
```python
class Solution:
    def reorderList(self, head):
        if not head:
            return None
            
        lsl = head
        rsl = None
        
        slow = head
        fast = head.next
        while slow and fast and fast.next:
            fast = fast.next.next
            slow = slow.next
        
        rsl = slow.next
        slow.next = None
        
        def rec(node):
            prev = None
            curr = node
            while curr:
                temp = curr.next
                curr.next = prev
                prev = curr
                curr = temp
            return prev
        
        rsl = rec(rsl)
        
        lptr = lsl
        while rsl:
            temp = rsl.next
            rsl.next = lptr.next
            lptr.next = rsl
            lptr = lptr.next.next
            rsl = temp
        
        return lsl
```
