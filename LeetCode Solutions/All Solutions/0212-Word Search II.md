---
title: "0212: Word Search II"
---
```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.end = False
     
    def addWord(self, word):
        temp = self
        for cx, c in enumerate(word):
            if c not in temp.children:
                temp.children[c] = TrieNode()
            temp = temp.children[c]
        temp.end = True

class Solution:
    def findWords(self, board, words):
	    
        root = TrieNode()
        for word in words:
            root.addWord(word)
        
        nR = len(board)
        nC = len(board[0])
        
        res = set()
        visit = set()
        def dfs(rx, cx, node, word):
            if 0 <= rx < nR and 0 <= cx < nC and (rx, cx) not in visit and board[rx][cx] in node.children:
                
                c = board[rx][cx]
                
                word.append(c)
                visit.add((rx, cx))
                
                node = node.children[c]
                
                if node.end: res.add("".join(word))
                
                dfs(rx + 1, cx, node, word)
                dfs(rx - 1, cx, node, word)
                dfs(rx, cx + 1, node, word)
                dfs(rx, cx - 1, node, word)
                
                visit.remove((rx, cx))
                word.pop()
        
        for rx in range(nR):
            for cx in range(nC):
                dfs(rx, cx, root, [])
                
        return list(res)
```