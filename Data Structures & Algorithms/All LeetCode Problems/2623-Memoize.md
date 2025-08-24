---
title: "2623: Memoize"
tags:
---
### Problem Statement

<p>Given a function <code>fn</code>, return a <strong>memoized</strong> version of that function.</p>

<p>A <strong>memoized </strong>function is a function that will never be called twice with the same inputs. Instead it will return a cached value.</p>

<p>You can assume there are <strong>3 </strong>possible input functions: <code>sum</code><strong>, </strong><code>fib</code><strong>, </strong>and <code>factorial</code><strong>.</strong></p>

<ul>
	<li><code>sum</code><strong> </strong>accepts two integers <code>a</code> and <code>b</code> and returns <code>a + b</code>. Assume that if a value has already been cached for the arguments <code>(b, a)</code> where <code>a != b</code>, it cannot be used for the arguments <code>(a, b)</code>. For example, if the arguments are <code>(3, 2)</code> and <code>(2, 3)</code>, two separate calls should be made.</li>
	<li><code>fib</code><strong> </strong>accepts a single integer <code>n</code> and returns <code>1</code> if <font face="monospace"><code>n &lt;= 1</code> </font>or<font face="monospace"> <code>fib(n - 1) + fib(n - 2)</code> </font>otherwise.</li>
	<li><code>factorial</code> accepts a single integer <code>n</code> and returns <code>1</code> if <code>n &lt;= 1</code> or <code>factorial(n - 1) * n</code> otherwise.</li>
</ul>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong>
fnName = &quot;sum&quot;
actions = [&quot;call&quot;,&quot;call&quot;,&quot;getCallCount&quot;,&quot;call&quot;,&quot;getCallCount&quot;]
values = [[2,2],[2,2],[],[1,2],[]]
<strong>Output:</strong> [4,4,1,3,2]
<strong>Explanation:</strong>
const sum = (a, b) =&gt; a + b;
const memoizedSum = memoize(sum);
memoizedSum(2, 2); // &quot;call&quot; - returns 4. sum() was called as (2, 2) was not seen before.
memoizedSum(2, 2); // &quot;call&quot; - returns 4. However sum() was not called because the same inputs were seen before.
// &quot;getCallCount&quot; - total call count: 1
memoizedSum(1, 2); // &quot;call&quot; - returns 3. sum() was called as (1, 2) was not seen before.
// &quot;getCallCount&quot; - total call count: 2
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:
</strong>fnName = &quot;factorial&quot;
actions = [&quot;call&quot;,&quot;call&quot;,&quot;call&quot;,&quot;getCallCount&quot;,&quot;call&quot;,&quot;getCallCount&quot;]
values = [[2],[3],[2],[],[3],[]]
<strong>Output:</strong> [2,6,2,2,6,2]
<strong>Explanation:</strong>
const factorial = (n) =&gt; (n &lt;= 1) ? 1 : (n * factorial(n - 1));
const memoFactorial = memoize(factorial);
memoFactorial(2); // &quot;call&quot; - returns 2.
memoFactorial(3); // &quot;call&quot; - returns 6.
memoFactorial(2); // &quot;call&quot; - returns 2. However factorial was not called because 2 was seen before.
// &quot;getCallCount&quot; - total call count: 2
memoFactorial(3); // &quot;call&quot; - returns 6. However factorial was not called because 3 was seen before.
// &quot;getCallCount&quot; - total call count: 2
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:
</strong>fnName = &quot;fib&quot;
actions = [&quot;call&quot;,&quot;getCallCount&quot;]
values = [[5],[]]
<strong>Output:</strong> [8,1]
<strong>Explanation:
</strong>fib(5) = 8 // &quot;call&quot;
// &quot;getCallCount&quot; - total call count: 1
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>0 &lt;= a, b &lt;= 10<sup>5</sup></code></li>
	<li><code>1 &lt;= n &lt;= 10</code></li>
	<li><code>1 &lt;= actions.length &lt;= 10<sup>5</sup></code></li>
	<li><code>actions.length === values.length</code></li>
	<li><code>actions[i]</code> is one of &quot;call&quot; and &quot;getCallCount&quot;</li>
	<li><code>fnName</code> is one of &quot;sum&quot;, &quot;factorial&quot; and &quot;fib&quot;</li>
</ul>


### Code Solution

```python

```
