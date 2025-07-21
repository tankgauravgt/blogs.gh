---
title: "0211: Design Add and Search Words Data Structure"
---
```python
class TrieNode:
    def __init__(self, val):
        self.val = val
        self.end = False
        self.children = {}

class WordDictionary:
    def __init__(self):
        self.root = TrieNode('')
    
    def addWord(self, word):
        temp = self.root
        for cx, c in enumerate(word):
            if c not in temp.children:
                temp.children[c] = TrieNode(c)
            temp = temp.children[c]
        temp.end = True
        
    def search(self, word):
        def rec_search(wx, word, init_node):
            wlen = len(word)
            temp = init_node
            for cx in range(wx, wlen):
                c = word[cx]
                if c == '.':
                    flag = False
                    for cc in temp.children:
                        flag = flag or rec_search(1 + cx, word, temp.children[cc])
                    return flag
                if c not in temp.children:
                    return False
                temp = temp.children[c]
            return temp.end
        return rec_search(0, word, self.root)
```
