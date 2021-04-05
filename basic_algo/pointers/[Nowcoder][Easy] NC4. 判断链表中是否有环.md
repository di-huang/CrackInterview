[NC4](https://www.nowcoder.com/practice/650474f313294468a4ded3ce0f7898b9?tpId=188&tqId=38026&rp=1&ru=%2Factivity%2Foj&qru=%2Fta%2Fjob-code-high-week%2Fquestion-ranking&tab=answerKey)
<br />
Space complexity is limited to O(1) for this question. <br />
<br />
**Algorithm:** <br />
Approach 1: <br />
Use faster and slower pointers: one takes one step at a time, the other takes two steps at a time. Return true if they are equal to each other, or return false if one of them is null. <br />
<br />
Approach 2: <br />
The next of each visited node is set to a common node (node_x) each recursion. Return true if node.next = node_x, or return false if node is null. <br />
