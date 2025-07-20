---
title: "0025: Reverse Nodes in k-Group"
---
```python
class Solution:
    def reverseKGroup(self, head, k):
	    
        def revk(node, k):
            prev = None
            curr = node
            while curr and k > 0:
                temp = curr.next
                curr.next = prev
                prev = curr
                curr = temp
                k = k - 1
            return prev, curr, k == 0
		
        dummy = ListNode(0)
        
        temp = dummy
        while head:
            done, head, completed = revk(head, k)
            temp.next = done if completed else revk(done, k)[0]
            while temp and temp.next:
                temp = temp.next
        return dummy.next
```
