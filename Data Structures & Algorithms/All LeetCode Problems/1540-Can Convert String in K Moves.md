---
title: "1540: Can Convert String in K Moves"
tags:
  - HashTable
  - String
---
### Problem Statement

<p>Given two strings <code>s</code> and <code>t</code>, your goal is to convert <code>s</code> into <code>t</code> in <code>k</code><strong> </strong>moves or less.</p>

<p>During the <code>i<sup>th</sup></code> (<font face="monospace"><code>1 &lt;= i &lt;= k</code>) </font>move you can:</p>

<ul>
	<li>Choose any index <code>j</code> (1-indexed) from <code>s</code>, such that <code>1 &lt;= j &lt;= s.length</code> and <code>j</code> has not been chosen in any previous move, and shift the character at that index <code>i</code> times.</li>
	<li>Do nothing.</li>
</ul>

<p>Shifting a character means replacing it by the next letter in the alphabet (wrapping around so that <code>&#39;z&#39;</code> becomes <code>&#39;a&#39;</code>). Shifting a character by <code>i</code> means applying the shift operations <code>i</code> times.</p>

<p>Remember that any index <code>j</code> can be picked at most once.</p>

<p>Return <code>true</code> if it&#39;s possible to convert <code>s</code> into <code>t</code> in no more than <code>k</code> moves, otherwise return <code>false</code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;input&quot;, t = &quot;ouput&quot;, k = 9
<strong>Output:</strong> true
<b>Explanation: </b>In the 6th move, we shift &#39;i&#39; 6 times to get &#39;o&#39;. And in the 7th move we shift &#39;n&#39; to get &#39;u&#39;.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;abc&quot;, t = &quot;bcd&quot;, k = 10
<strong>Output:</strong> false
<strong>Explanation: </strong>We need to shift each character in s one time to convert it into t. We can shift &#39;a&#39; to &#39;b&#39; during the 1st move. However, there is no way to shift the other characters in the remaining moves to obtain t from s.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;aab&quot;, t = &quot;bbb&quot;, k = 27
<strong>Output:</strong> true
<b>Explanation: </b>In the 1st move, we shift the first &#39;a&#39; 1 time to get &#39;b&#39;. In the 27th move, we shift the second &#39;a&#39; 27 times to get &#39;b&#39;.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length, t.length &lt;= 10^5</code></li>
	<li><code>0 &lt;= k &lt;= 10^9</code></li>
	<li><code>s</code>, <code>t</code> contain only lowercase English letters.</li>
</ul>


### Code Solution

```python

```
