---
title: "0010: Regular Expression Matching"
tags:
  - String
  - DynamicProgramming
  - Recursion
---
### Problem Statement

<p>Given an input string <code>s</code> and a pattern <code>p</code>, implement regular expression matching with support for <code>&#39;.&#39;</code> and <code>&#39;*&#39;</code> where:</p>

<ul>
	<li><code>&#39;.&#39;</code> Matches any single character.​​​​</li>
	<li><code>&#39;*&#39;</code> Matches zero or more of the preceding element.</li>
</ul>

<p>The matching should cover the <strong>entire</strong> input string (not partial).</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;aa&quot;, p = &quot;a&quot;
<strong>Output:</strong> false
<strong>Explanation:</strong> &quot;a&quot; does not match the entire string &quot;aa&quot;.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;aa&quot;, p = &quot;a*&quot;
<strong>Output:</strong> true
<strong>Explanation:</strong> &#39;*&#39; means zero or more of the preceding element, &#39;a&#39;. Therefore, by repeating &#39;a&#39; once, it becomes &quot;aa&quot;.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;ab&quot;, p = &quot;.*&quot;
<strong>Output:</strong> true
<strong>Explanation:</strong> &quot;.*&quot; means &quot;zero or more (*) of any character (.)&quot;.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 20</code></li>
	<li><code>1 &lt;= p.length &lt;= 20</code></li>
	<li><code>s</code> contains only lowercase English letters.</li>
	<li><code>p</code> contains only lowercase English letters, <code>&#39;.&#39;</code>, and <code>&#39;*&#39;</code>.</li>
	<li>It is guaranteed for each appearance of the character <code>&#39;*&#39;</code>, there will be a previous valid character to match.</li>
</ul>


### Code Solution

```python
class Solution:
    def isMatch(self, s: str, p: str) -> bool:
        
        @cache
        def rec(s1, p1):
            # boundary conditions:
            if s1 > len(s) or p1 > len(p):
                return False
            if p1 == len(p):
                return s1 == len(s)
            
            # check if pattern is matching:
            matched = (s1 < len(s) and p1 < len(p)) and p[p1] in {'.', s[s1]}
            
            if p1 + 1 < len(p) and p[p1 + 1] == '*':
                take_it = rec(s1 + 1, p1)
                skip_it = rec(s1, p1 + 2)
                return (matched and take_it) or skip_it
            elif matched:
                return rec(s1 + 1, p1 + 1)
            
            return False
        
        return rec(0, 0)
```
