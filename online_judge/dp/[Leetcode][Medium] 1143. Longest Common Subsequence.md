https://leetcode.com/problems/longest-common-subsequence/

**Algorithm:** <br />
dp[n][m] = dp[n - 1][m - 1] + 1 if text1[n] == text2[m]; <br />
Otherwise, dp[n][m] = max(dp[n - 1][m], dp[n][m - 1]) <br />

**Time Complexity** <br />
O(N * M)
