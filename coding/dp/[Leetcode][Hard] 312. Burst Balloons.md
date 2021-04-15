https://leetcode-cn.com/problems/burst-balloons/ <br />

**Algorithm:** <br />
Let dp[i][j] denote the maximum coins on nums[i:j]. Assume that the current burst position is k (i <= k <= j), we can derive the following dp equation: <br />
````
dp[i][j] = max(dp[i][j], dp[i][k - 1] + dp[k + 1][j] + nums[k] * nums[i - 1] * nums[j + 1])
````
We start with smaller length so that `dp[i][k - 1]` and `dp[k + 1][j]` are subproblems. <br />
