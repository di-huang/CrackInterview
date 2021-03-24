https://leetcode.com/problems/partition-labels/

Save the (start, end) indices of letters in the string S; <br />
<br />
For c = 1st letter in loop { <br />
Get the (start, end) indices of c; <br />
From start to end, make sure that each letter only appears in the current part, otherwise, we extend this part until the above condition is met; <br />
Record the size of this part; <br />
Update c = S[end + 1]; <br />
}

**Time Complexity** <br />
O(n)
