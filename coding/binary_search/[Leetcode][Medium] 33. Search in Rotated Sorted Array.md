https://leetcode-cn.com/problems/search-in-rotated-sorted-array/ <br />

**Algorithm:** <br />
```
Situation 1:
left........mid...rotation....right
A: [left, mid]
B: [mid, rotation]
C: [rotation, right]
First: nums[0]

or

Situation 2:
left........rotation...mid....right
D: [left, rotation]
E: [rotation, mid]
F: [mid, right]
```
1. In while loop (while left <= right), return nums[mid] if nums[mid] == target <br />
2. For Situation 1, `right = mid - 1` if target in A; otherwise, `left = mid + 1` <br />
2. For Situation 2, `left = mid + 1` if target in F; otherwise, `right = mid - 1` <br />

**Time Complexity** <br />
O(logN)
