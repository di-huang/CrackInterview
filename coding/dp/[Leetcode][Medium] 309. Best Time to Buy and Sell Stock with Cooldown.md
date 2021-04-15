https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/ <br />

**Algorithm:** <br />
Approach 1: <br />
````python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
    	# 0: buy
    	# 1: sell
    	# 2: cooldown
        dp = [ [0] * 3 for i in range(len(prices)) ]
        dp[0][0] = -prices[0]
        for i in range(1, len(prices)):
            dp[i][0] = max(dp[i - 1][0], dp[i - 1][2] - prices[i])
            dp[i][1] = max(dp[i - 1][1], dp[i - 1][0] + prices[i])
            dp[i][2] = max(dp[i - 1][0], dp[i - 1][1], dp[i - 1][2])
        return dp[-1][1]
````

Approach 2: <br />
````python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # f[i][0]: the maximum profit when holding stock
        # f[i][1]: the maximum profit when not holding stock in the cooldown period
        # f[i][2]: the maximum profit when not holding stock and not in the cooldown period
        n = len(prices)
        dp = [ [0] * 3 for i in range(n) ]
        dp[0][0] = -prices[0]
        for i in range(1, n):
            dp[i][0] = max(dp[i - 1][0], dp[i - 1][2] - prices[i])
            dp[i][1] = dp[i - 1][0] + prices[i]
            dp[i][2] = max(dp[i - 1][1], dp[i - 1][2])
        return max(dp[n - 1][1], dp[n - 1][2])
````