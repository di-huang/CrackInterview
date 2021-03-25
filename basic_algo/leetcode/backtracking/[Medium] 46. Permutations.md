https://leetcode.com/problems/permutations/

**Algorithm:** <br />
Implement backtracking via a recursive function. <br />
The base case: append the current combination (comb) to the result if the candidate list is empty; <br />
The recursive cases: go through the candidate list (append each element to comb, concatenate the list and make recursive call, backtrack and remove the last element of comb); <br />

**Time Complexity** <br />
O(n!)
