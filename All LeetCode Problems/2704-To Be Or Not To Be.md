---
title: "2704: To Be Or Not To Be"
tags:
---
### Problem Statement

<p>Write a function <code>expect</code> that helps developers test their code. It should take in any value <code>val</code> and return an object with the following two functions.</p>

<ul>
	<li><code>toBe(val)</code> accepts another value and returns <code>true</code> if the two values <code>===</code> each other. If they are not equal, it should throw an error <code>&quot;Not Equal&quot;</code>.</li>
	<li><code>notToBe(val)</code> accepts another value and returns <code>true</code> if the two values <code>!==</code> each other. If they are equal, it should throw an error <code>&quot;Equal&quot;</code>.</li>
</ul>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> func = () =&gt; expect(5).toBe(5)
<strong>Output:</strong> {&quot;value&quot;: true}
<strong>Explanation:</strong> 5 === 5 so this expression returns true.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> func = () =&gt; expect(5).toBe(null)
<strong>Output:</strong> {&quot;error&quot;: &quot;Not Equal&quot;}
<strong>Explanation:</strong> 5 !== null so this expression throw the error &quot;Not Equal&quot;.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> func = () =&gt; expect(5).notToBe(null)
<strong>Output:</strong> {&quot;value&quot;: true}
<strong>Explanation:</strong> 5 !== null so this expression returns true.
</pre>


### Code Solution

```python

```
