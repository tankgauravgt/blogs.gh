---
title: "0676: Implement Magic Dictionary"
tags:
  - HashTable
  - String
  - Depth-FirstSearch
  - Design
  - Trie
---
### Problem Statement

<p>Design a data structure that is initialized with a list of <strong>different</strong> words. Provided a string, you should determine if you can change exactly one character in this string to match any word in the data structure.</p>

<p>Implement the <code>MagicDictionary</code> class:</p>

<ul>
	<li><code>MagicDictionary()</code> Initializes the object.</li>
	<li><code>void buildDict(String[] dictionary)</code> Sets the data structure with an array of distinct strings <code>dictionary</code>.</li>
	<li><code>bool search(String searchWord)</code> Returns <code>true</code> if you can change <strong>exactly one character</strong> in <code>searchWord</code> to match any string in the data structure, otherwise returns <code>false</code>.</li>
</ul>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input</strong>
[&quot;MagicDictionary&quot;, &quot;buildDict&quot;, &quot;search&quot;, &quot;search&quot;, &quot;search&quot;, &quot;search&quot;]
[[], [[&quot;hello&quot;, &quot;leetcode&quot;]], [&quot;hello&quot;], [&quot;hhllo&quot;], [&quot;hell&quot;], [&quot;leetcoded&quot;]]
<strong>Output</strong>
[null, null, false, true, false, false]

<strong>Explanation</strong>
MagicDictionary magicDictionary = new MagicDictionary();
magicDictionary.buildDict([&quot;hello&quot;, &quot;leetcode&quot;]);
magicDictionary.search(&quot;hello&quot;); // return False
magicDictionary.search(&quot;hhllo&quot;); // We can change the second &#39;h&#39; to &#39;e&#39; to match &quot;hello&quot; so we return True
magicDictionary.search(&quot;hell&quot;); // return False
magicDictionary.search(&quot;leetcoded&quot;); // return False
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= dictionary.length &lt;= 100</code></li>
	<li><code>1 &lt;= dictionary[i].length &lt;= 100</code></li>
	<li><code>dictionary[i]</code> consists of only lower-case English letters.</li>
	<li>All the strings in <code>dictionary</code> are <strong>distinct</strong>.</li>
	<li><code>1 &lt;= searchWord.length &lt;= 100</code></li>
	<li><code>searchWord</code> consists of only lower-case English letters.</li>
	<li><code>buildDict</code> will be called only once before <code>search</code>.</li>
	<li>At most <code>100</code> calls will be made to <code>search</code>.</li>
</ul>


### Code Solution

```python

```
