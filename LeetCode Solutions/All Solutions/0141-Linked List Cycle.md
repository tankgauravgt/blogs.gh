---
title: "0141: Linked List Cycle"
---
```python
class Solution:
    def hasCycle(self, head):
	    
        if not head:
            return False
        
        slow = head
        fast = head.next
        
        while slow and fast and fast.next:
            fast = fast.next.next
            slow = slow.next
            if slow == fast:
                return True
        
        return False
```