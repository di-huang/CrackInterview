https://leetcode.com/problems/minimum-number-of-taps-to-open-to-water-a-garden/submissions/ <br />
Similar to https://www.nowcoder.com/questionTerminal/61e1e66e39f348cdb6495de91ac36a41 <br />

**Algorithm:** <br />
Greedy: keep finding the farthest right coverage border and make sure it will cover the current position at the same time. <br />
````python
class Solution:
    def custom(self, x, y):
        return y[1] - x[1]

    def minTaps(self, n: int, ranges: List[int]) -> int:
        ranges1 = []
        for i in range(len(ranges)):
            ranges1.append((i - ranges[i], i + ranges[i]))
        ranges1 = sorted(ranges1, key=cmp_to_key(self.custom))
        
        res, cur = 0, 0
        while cur < n:
            found = False
            for i in range(len(ranges1)):
                if ranges1[i][0] <= cur and cur <= ranges1[i][1]:
                    found = True
                    res += 1
                    cur = ranges1[i][1]
                    ranges1.pop(i)
                    break
            if not found:
                return -1
        return res
````