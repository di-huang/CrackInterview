https://leetcode.com/problems/counting-bits/

**Algorithm:** <br />
Examples: <br />
0 --> 0 <br />
1 --> 1 <br />
2 --> 10 <br />
3 --> 11 <br />
4 --> 100 <br />
5 --> 101 <br />
6 --> 110 <br />
7 --> 111 <br />
8 --> 1000 <br />
...<br />
<br />
From 2^1 to 2^2 - 1, dp[2] = dp[0] + 1, dp[3] = dp[1] + 1 <br />
From 2^2 to 2^3 - 1, dp[4] = dp[0] + 1, dp[5] = dp[1] + 1, dp[6] = dp[2] + 1, dp[7] = dp[3] + 1 <br />
...<br />
Thus, dp[i] = dp[i - k] + 1 where k = 2^(int(log2(i)))

**Time Complexity** <br />
O(n)
