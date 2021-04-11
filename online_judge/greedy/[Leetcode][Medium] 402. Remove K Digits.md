https://leetcode-cn.com/problems/remove-k-digits/ <br />

**Algorithm:** <br />
Use a stack to track the candidate number and append digit to it each iteration. Drop the tops which are bigger than the current digit until k is used up. Removig k digits is equivalent to keep (len(num) - k) digits in the end. Return stack[:len(num) - k].

**Time Complexity:** <br />
O(N)
