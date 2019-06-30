<!--|This file generated by command(leetcode description); DO NOT EDIT.    |-->
<!--+----------------------------------------------------------------------+-->
<!--|@author    Openset <openset.wang@gmail.com>                           |-->
<!--|@link      https://github.com/openset                                 |-->
<!--|@home      https://github.com/openset/leetcode                        |-->
<!--+----------------------------------------------------------------------+-->

[< Previous](https://github.com/openset/leetcode/tree/master/problems/find-k-length-substrings-with-no-repeated-characters "Find K-Length Substrings With No Repeated Characters")
　　　　　　　　　　　　　　　　
[Next >](https://github.com/openset/leetcode/tree/master/problems/path-with-maximum-minimum-value "Path With Maximum Minimum Value")

## 5023. The Earliest Moment When Everyone Become Friends (Medium)

<p>In a social group, there are <code>N</code> people, with unique integer ids from <code>0</code> to <code>N-1</code>.</p>

<p>We have a list of <code>logs</code>, where each <code>logs[i] = [timestamp, id_A, id_B]</code> contains a non-negative&nbsp;integer timestamp, and the ids of two different people.</p>

<p>Each log represents the time in which two different people became friends. &nbsp;Friendship is symmetric: if A is friends with B, then B is friends with A.</p>

<p>Let&#39;s say that person A is acquainted with person B if A is friends with B, or A is a friend of someone acquainted with B.</p>

<p>Return the earliest time for which every person became acquainted with every other person. Return -1 if there is no&nbsp;such&nbsp;earliest time.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong>logs = <span id="example-input-1-1">[[20190101,0,1],[20190104,3,4],[20190107,2,3],[20190211,1,5],[20190224,2,4],[20190301,0,3],[20190312,1,2],[20190322,4,5]]</span>, N = <span id="example-input-1-2">6</span>
<strong>Output: </strong><span id="example-output-1">20190301</span>
<strong>Explanation: </strong>
The first event occurs at timestamp = 20190101 and after 0 and 1 become friends we have the following friendship groups [0,1], [2], [3], [4], [5].
The second event occurs at timestamp = 20190104 and after 3 and 4 become friends we have the following friendship groups [0,1], [2], [3,4], [5].
The third event occurs at timestamp = 20190107 and after 2 and 3 become friends we have the following friendship groups [0,1], [2,3,4], [5].
The fourth event occurs at timestamp = 20190211 and after 1 and 5 become friends we have the following friendship groups [0,1,5], [2,3,4].
The fifth event occurs at timestamp = 20190224 and as 2 and 4 are already friend anything happens.
The sixth event occurs at timestamp = 20190301 and after 0 and 3 become friends we have that all become friends.
</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong></p>

<ol>
	<li><code>1 &lt;= N &lt;= 100</code></li>
	<li><code>1 &lt;= logs.length &lt;= 10^4</code></li>
	<li><code>0 &lt;= logs[i][0] &lt;= 10^9</code></li>
	<li><code>0 &lt;= logs[i][1], logs[i][2] &lt;= N - 1</code></li>
	<li>It&#39;s guaranteed that all timestamps in logs[i][0] are different.</li>
	<li><code>Logs </code>are not necessarily ordered by some criteria.</li>
	<li><code>logs[i][1] != logs[i][2]</code></li>
</ol>

### Related Topics
  [[Union Find](https://github.com/openset/leetcode/tree/master/tag/union-find/README.md)]

### Similar Questions
  1. [Friend Circles](https://github.com/openset/leetcode/tree/master/problems/friend-circles) (Medium)

### Hints
<details>
<summary>Hint 1</summary>
Sort the log items by their timestamp.
</details>

<details>
<summary>Hint 2</summary>
How can we model this problem as a graph problem?
</details>

<details>
<summary>Hint 3</summary>
Let's use a union-find data structure. At the beginning we have a graph with N nodes but no edges.
</details>

<details>
<summary>Hint 4</summary>
Then we loop through the events and if unite each node until the number of connected components reach to 1. Notice that each time two different connected components are united the number of connected components decreases by 1.
</details>