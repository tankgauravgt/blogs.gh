---
title: "0212: Word Search II"
tags:
  - Array
  - String
  - Backtracking
  - Trie
  - Matrix
---
### Problem Statement

<p>Given an <code>m x n</code> <code>board</code> of characters and a list of strings <code>words</code>, return <em>all words on the board</em>.</p>

<p>Each word must be constructed from letters of sequentially adjacent cells, where <strong>adjacent cells</strong> are horizontally or vertically neighboring. The same letter cell may not be used more than once in a word.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/07/search1.jpg" style="width: 322px; height: 322px;" />
<pre>
<strong>Input:</strong> board = [[&quot;o&quot;,&quot;a&quot;,&quot;a&quot;,&quot;n&quot;],[&quot;e&quot;,&quot;t&quot;,&quot;a&quot;,&quot;e&quot;],[&quot;i&quot;,&quot;h&quot;,&quot;k&quot;,&quot;r&quot;],[&quot;i&quot;,&quot;f&quot;,&quot;l&quot;,&quot;v&quot;]], words = [&quot;oath&quot;,&quot;pea&quot;,&quot;eat&quot;,&quot;rain&quot;]
<strong>Output:</strong> [&quot;eat&quot;,&quot;oath&quot;]
</pre>

<p><strong class="example">Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/07/search2.jpg" style="width: 162px; height: 162px;" />
<pre>
<strong>Input:</strong> board = [[&quot;a&quot;,&quot;b&quot;],[&quot;c&quot;,&quot;d&quot;]], words = [&quot;abcb&quot;]
<strong>Output:</strong> []
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>m == board.length</code></li>
	<li><code>n == board[i].length</code></li>
	<li><code>1 &lt;= m, n &lt;= 12</code></li>
	<li><code>board[i][j]</code> is a lowercase English letter.</li>
	<li><code>1 &lt;= words.length &lt;= 3 * 10<sup>4</sup></code></li>
	<li><code>1 &lt;= words[i].length &lt;= 10</code></li>
	<li><code>words[i]</code> consists of lowercase English letters.</li>
	<li>All the strings of <code>words</code> are unique.</li>
</ul>


### Code Solution

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
