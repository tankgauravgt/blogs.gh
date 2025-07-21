---
title: "0206: Reverse Linked List"
---
```python
class Solution:
    def reverseList(self, head):
	    
        def rev(node):
            prev = None
            curr = node
            while curr:
                temp = curr.next
                curr.next = prev
                prev = curr
                curr = temp
            return prev
        
        return rev(head)
```