https://leetcode-cn.com/problems/longest-palindromic-substring/ <br />

**Algorithm:** <br />
1. The first loop: for L in [2, n] <br />
2. The second loop: for i in [0, n + 1 - L) <br />
3. Set j = L + i - 1, which is the rightmost index of substring
4. If s[i] == s[j]: dp[i][j] = dp[i + 1][j - 1] and dp[i][j] = True when L <= 3 <br />
5. Update max_palin_len and the begin index <br />

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        n = len(s)
        if n < 2:
            return s

        max_len, begin = 1, 0
        dp = [[False] * n for _ in range(n)]
        for i in range(n):
            dp[i][i] = True

        for L in range(2, n + 1):
            for i in range(n + 1 - L):
                j = L + i - 1
                if s[i] == s[j]:
                    dp[i][j] = True if L <= 3 else dp[i + 1][j - 1]
                    if dp[i][j] and L > max_len:
                        max_len, begin = L, i
        return s[begin : begin + max_len]
```