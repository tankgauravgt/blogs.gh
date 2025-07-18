---
title: "0023: Merge k Sorted Lists"
---
```python
import heapq

class LNWrap:
    def __init__(self, node):
        self.node = node
        
    def __lt__(self, other):
        return self.node.val < other.node.val
        
    def get(self):
        return self.node
        
class Solution:
    def mergeKLists(self, lists):
        
        hq = []
        for lst in lists:
            if lst != None:
                hq.append(LNWrap(lst))
        
        heapq.heapify(hq)
        
        head = temp = ListNode(-1, None)
        while hq:
            lst = heapq.heappop(hq)
            temp.next = ListNode(lst.get().val, None)
            temp = temp.next
            if lst.get().next:
                heapq.heappush(hq, LNWrap(lst.get().next))
        
        return head.next
```
