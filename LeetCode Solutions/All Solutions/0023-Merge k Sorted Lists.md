---
title: "0023: Merge k Sorted Lists"
---
```python
import heapq


class CustomNode:
	
    def __init__(self, node):
        self.node = node
    
    def __lt__(self, other):
        return self.node.val < other.node.val


class Solution:
    def mergeKLists(self, lists):
	    
        hq = []
        for l in lists:
            if not l: continue
            heapq.heappush(hq, CustomNode(l))
        
        dummy = temp = ListNode(0)
        
        while hq:
            curr_node = heapq.heappop(hq)
            temp.next = ListNode(curr_node.node.val)
            temp = temp.next
            next_node = curr_node.node.next
            if next_node:
                heapq.heappush(hq, CustomNode(next_node))
        
        return dummy.next
```
