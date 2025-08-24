---
title: "0022: Generate Parentheses"
tags:
  - String
  - DynamicProgramming
  - Backtracking
---
### Problem Statement

<p>Given <code>n</code> pairs of parentheses, write a function to <em>generate all combinations of well-formed parentheses</em>.</p>


<p><strong class="example">Example 1:</strong></p>
<pre><strong>Input:</strong> n = 3
<strong>Output:</strong> ["((()))","(()())","(())()","()(())","()()()"]
</pre><p><strong class="example">Example 2:</strong></p>
<pre><strong>Input:</strong> n = 1
<strong>Output:</strong> ["()"]
</pre>

<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= n &lt;= 8</code></li>
</ul>


### Code Solution

```python
class Solution:
    def generateParenthesis(self, n):
	    
        def generate(ob, cb, buf, output):
            if cb > ob:
                return
            if len(buf) == 2 * n:
                output.append("".join(buf))
                return
            if ob < n:
                buf.append('(')
                generate(ob + 1, cb, buf, output)
                buf.pop()
            buf.append(')')
            generate(ob, cb + 1, buf, output)
            buf.pop()
        
        result = []
        generate(0, 0, [], result)
        return result
```
