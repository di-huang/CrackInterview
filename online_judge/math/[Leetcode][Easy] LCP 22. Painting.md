https://leetcode-cn.com/problems/ccw6C7/ <br />

**Algorithm:** <br />
The number of black grids = (i + j) * n - i * j where i and j denote i rows and j columns. Use math combination to calculate the number of painting ways.<br />
````python
class Solution:
    def paintingPlan(self, n: int, k: int) -> int:
        if k == 0 or k == n * n:
            return 1
        if k < n:
            return 0

        res = 0
        for i in range(n):
            for j in range(n):
                if (i + j) * n - i * j == k:
                    res += comb(n, i) * comb(n, j)
        return res
````

