https://leetcode-cn.com/problems/candy/ <br />

**Algorithm:** <br />
1. Initialize candies = [1] * len(ratings) <br />
2. Scan from left to right and update candies[i] = candies[i - 1] + 1 if ratings[i] > ratings[i - 1] <br />
3. Scan from right to left and update candies[i] = max(candies[i], candies[i + 1] + 1) if ratings[i] > ratings[i + 1] <br />
4. Return sum(candies) <br />

**Time Complexity:** <br />
O(N)