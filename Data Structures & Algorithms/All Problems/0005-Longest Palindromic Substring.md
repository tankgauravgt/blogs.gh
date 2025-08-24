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
    def longestPalindrome(self, s):
        N = len(s)
        cmax = 0
        output = ""
        for ix in range(N):
            lx = rx = ix
            while lx >= 0 and rx < N and s[lx] == s[rx]:
                if cmax < rx - lx + 1:
                    output = s[lx:1 + rx]
                    cmax = rx - lx + 1
                lx = lx - 1
                rx = rx + 1
        for ix in range(N - 1):
            lx = ix
            rx = ix + 1
            while lx >= 0 and rx < N and s[lx] == s[rx]:
                if cmax < rx - lx + 1:
                    output = s[lx:1 + rx]
                    cmax = rx - lx + 1
                lx = lx - 1
                rx = rx + 1        
        return output
```
