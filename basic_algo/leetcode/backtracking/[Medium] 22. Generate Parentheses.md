https://leetcode.com/problems/generate-parentheses/

**Algorithm:** <br />
The base case: append the current combination (comb) to the result if # of left parenthesis (left) and # of right parenthesis (right) are both equal to n; <br />
The recursive cases:
1. append '(', make recursive call and backtrack if right < n and left < n; <br />
2. append ')', make recursive call and backtrack if right < left and right < n; <br />

**Time Complexity** <br />
