https://leetcode.com/problems/edit-distance/
Similar to [Nowcoder](https://www.nowcoder.com/practice/3959837097c7413a961a135d7104c314?tpId=37&tqId=21275&rp=1&ru=%2Fta%2Fhuawei&qru=%2Fta%2Fhuawei%2Fquestion-ranking&tab=answerKey)

**Algorithm:** <br />
dp[n][m] = min(dp[n - 1][m] + 1, dp[n][m - 1] + 1, dp[n - 1][m - 1] if word1[n] == word2[m] else dp[n - 1][m - 1] + 1) <br />

**Time Complexity** <br />
O(N * M)
