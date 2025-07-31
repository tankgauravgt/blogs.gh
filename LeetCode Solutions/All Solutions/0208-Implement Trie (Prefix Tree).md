---
title: "0208: Implement Trie (Prefix Tree)"
---
```python
class TNode:
    def __init__(self, val):
        self.val = val
        self.end = False
        self.children = {}
        
class Trie:
    def __init__(self):
        self.root = TNode('')
        
    def insert(self, word):
        temp = self.root
        for cx, c in enumerate(word):
            if c not in temp.children:
                temp.children[c] = TNode(c)
            temp = temp.children[c]
        temp.end = True
    
    def search(self, word):
        temp = self.root
        for c in word:
            if c not in temp.children:
                return False
            temp = temp.children[c]
        return temp.end
	    
    def startsWith(self, prefix):
        temp = self.root
        for c in prefix:
            if c not in temp.children:
                return False
            temp = temp.children[c]
        return True
```
