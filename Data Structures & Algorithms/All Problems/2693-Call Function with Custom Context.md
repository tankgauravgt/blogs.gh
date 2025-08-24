---
title: "2693: Call Function with Custom Context"
tags:
---
### Problem Statement

<p>Enhance all functions to have the <code>callPolyfill</code> method. The method accepts an object <code>obj</code> as its first parameter and any number of additional arguments. The <code>obj</code> becomes the <code>this</code> context for the function. The additional arguments are passed to the function (that the <code>callPolyfill</code> method belongs on).</p>

<p>For example if you had the function:</p>

<pre>
function tax(price, taxRate) {
  const totalCost = price * (1 + taxRate);
  console.log(`The cost of ${this.item} is ${totalCost}`);
}
</pre>

<p>Calling this function like <code>tax(10, 0.1)</code> will log <code>&quot;The cost of undefined is 11&quot;</code>. This is because the <code>this</code> context was not defined.</p>

<p>However, calling the function like <code>tax.callPolyfill({item: &quot;salad&quot;}, 10, 0.1)</code> will log <code>&quot;The cost of salad is 11&quot;</code>. The <code>this</code> context was appropriately set, and the function logged an appropriate output.</p>

<p>Please solve this without using the built-in <code>Function.call</code> method.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong>
fn = function add(b) {
  return this.a + b;
}
args = [{&quot;a&quot;: 5}, 7]
<strong>Output:</strong> 12
<strong>Explanation:</strong>
fn.callPolyfill({&quot;a&quot;: 5}, 7); // 12
callPolyfill sets the &quot;this&quot; context to {&quot;a&quot;: 5}. 7 is passed as an argument.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> 
fn = function tax(price, taxRate) { 
 return `The cost of the ${this.item} is ${price * taxRate}`; 
}
args = [{&quot;item&quot;: &quot;burger&quot;}, 10, 1.1]
<strong>Output:</strong> &quot;The cost of the burger is 11&quot;
<strong>Explanation:</strong> callPolyfill sets the &quot;this&quot; context to {&quot;item&quot;: &quot;burger&quot;}. 10 and 1.1 are passed as additional arguments.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code><font face="monospace">typeof args[0] == &#39;object&#39; and args[0] != null</font></code></li>
	<li><code>1 &lt;= args.length &lt;= 100</code></li>
	<li><code>2 &lt;= JSON.stringify(args[0]).length &lt;= 10<sup>5</sup></code></li>
</ul>


### Code Solution

```python

```
