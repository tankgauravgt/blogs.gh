---
title: "0005: Longest Palindromic Substring"
tags:
  - TwoPointers
  - String
  - DynamicProgramming
---
### Problem Statement

<p>Given a string <code>s</code>, return <em>the longest</em> <span data-keyword="palindromic-string"><em>palindromic</em></span> <span data-keyword="substring-nonempty"><em>substring</em></span> in <code>s</code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;babad&quot;
<strong>Output:</strong> &quot;bab&quot;
<strong>Explanation:</strong> &quot;aba&quot; is also a valid answer.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;cbbd&quot;
<strong>Output:</strong> &quot;bb&quot;
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 1000</code></li>
	<li><code>s</code> consist of only digits and English letters.</li>
</ul>


### Code Solution

```python
class Solution:
    
    def expand(self, s, lx, rx):
        while lx >= 0 and rx <= len(s) - 1 and  s[lx] == s[rx]:
            lx = lx - 1
            rx = rx + 1
        return s[1 + lx:rx]
        
    def longestPalindrome(self, s: str) -> str:
        N = len(s)
        
        cmax = ""
        for ix in range(N):
            if ix != 0:
                cmax = max(cmax, self.expand(s, ix, ix - 1), key=len)
            cmax = max(cmax, self.expand(s, ix, ix), key=len)
        return cmax
```
