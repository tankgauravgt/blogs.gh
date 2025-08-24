---
title: "0211: Design Add and Search Words Data Structure"
tags:
  - String
  - Depth-FirstSearch
  - Design
  - Trie
---
### Problem Statement

<p>Design a data structure that supports adding new words and finding if a string matches any previously added string.</p>

<p>Implement the <code>WordDictionary</code> class:</p>

<ul>
	<li><code>WordDictionary()</code> Initializes the object.</li>
	<li><code>void addWord(word)</code> Adds <code>word</code> to the data structure, it can be matched later.</li>
	<li><code>bool search(word)</code> Returns <code>true</code> if there is any string in the data structure that matches <code>word</code> or <code>false</code> otherwise. <code>word</code> may contain dots <code>&#39;.&#39;</code> where dots can be matched with any letter.</li>
</ul>


<p><strong class="example">Example:</strong></p>

<pre>
<strong>Input</strong>
[&quot;WordDictionary&quot;,&quot;addWord&quot;,&quot;addWord&quot;,&quot;addWord&quot;,&quot;search&quot;,&quot;search&quot;,&quot;search&quot;,&quot;search&quot;]
[[],[&quot;bad&quot;],[&quot;dad&quot;],[&quot;mad&quot;],[&quot;pad&quot;],[&quot;bad&quot;],[&quot;.ad&quot;],[&quot;b..&quot;]]
<strong>Output</strong>
[null,null,null,null,false,true,true,true]

<strong>Explanation</strong>
WordDictionary wordDictionary = new WordDictionary();
wordDictionary.addWord(&quot;bad&quot;);
wordDictionary.addWord(&quot;dad&quot;);
wordDictionary.addWord(&quot;mad&quot;);
wordDictionary.search(&quot;pad&quot;); // return False
wordDictionary.search(&quot;bad&quot;); // return True
wordDictionary.search(&quot;.ad&quot;); // return True
wordDictionary.search(&quot;b..&quot;); // return True
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= word.length &lt;= 25</code></li>
	<li><code>word</code> in <code>addWord</code> consists of lowercase English letters.</li>
	<li><code>word</code> in <code>search</code> consist of <code>&#39;.&#39;</code> or lowercase English letters.</li>
	<li>There will be at most <code>2</code> dots in <code>word</code> for <code>search</code> queries.</li>
	<li>At most <code>10<sup>4</sup></code> calls will be made to <code>addWord</code> and <code>search</code>.</li>
</ul>


### Code Solution

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
