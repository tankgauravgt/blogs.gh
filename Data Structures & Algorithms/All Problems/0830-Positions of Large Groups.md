---
title: "0830: Positions of Large Groups"
tags:
  - String
---
### Problem Statement

<p>In a string <code><font face="monospace">s</font></code> of lowercase letters, these letters form consecutive groups of the same character.</p>

<p>For example, a string like <code>s = &quot;abbxxxxzyy&quot;</code> has the groups <code>&quot;a&quot;</code>, <code>&quot;bb&quot;</code>, <code>&quot;xxxx&quot;</code>, <code>&quot;z&quot;</code>, and <code>&quot;yy&quot;</code>.</p>

<p>A group is identified by an interval <code>[start, end]</code>, where <code>start</code> and <code>end</code> denote the start and end indices (inclusive) of the group. In the above example, <code>&quot;xxxx&quot;</code> has the interval <code>[3,6]</code>.</p>

<p>A group is considered <strong>large</strong> if it has 3 or more characters.</p>

<p>Return <em>the intervals of every <strong>large</strong> group sorted in <strong>increasing order by start index</strong></em>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;abbxxxxzzy&quot;
<strong>Output:</strong> [[3,6]]
<strong>Explanation:</strong> <code>&quot;xxxx&quot; is the only </code>large group with start index 3 and end index 6.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;abc&quot;
<strong>Output:</strong> []
<strong>Explanation:</strong> We have groups &quot;a&quot;, &quot;b&quot;, and &quot;c&quot;, none of which are large groups.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;abcdddeeeeaabbbcd&quot;
<strong>Output:</strong> [[3,5],[6,9],[12,14]]
<strong>Explanation:</strong> The large groups are &quot;ddd&quot;, &quot;eeee&quot;, and &quot;bbb&quot;.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 1000</code></li>
	<li><code>s</code> contains lowercase English letters only.</li>
</ul>


### Code Solution

```python

```
