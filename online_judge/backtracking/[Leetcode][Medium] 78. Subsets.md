https://leetcode.com/problems/subsets/

**Algorithm:** <br />
For each recursion, we have two choices: 1. append the current element to temp and backtrack afterwards; 2. do nothing; <br />
When index reaches to the end of num, we append temp to res. <br />

**Time Complexity** <br />
O(2^n)
