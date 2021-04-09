https://leetcode.com/problems/count-nice-pairs-in-an-array/ <br />

**Algorithm:** <br />
Brute force (time limit exceeded): <br />
````python
class Solution:
    def countNicePairs(self, nums: List[int]) -> int:
        D = {}
        N = len(nums)
        res = 0
        for i in range(N - 1):
            for j in range(i + 1, N):
                ar, br = 0, 0
                if nums[i] not in D:
                    D[nums[i]] = int(str(nums[i])[::-1])
                ar = D[nums[i]]

                if nums[j] not in D:
                    D[nums[j]] = int(str(nums[j])[::-1])
                br = D[nums[j]]

                if ar + nums[j] == br + nums[i]:
                    res += 1

        return res % 1000000007
````

Use Hashmap to store the difference between x and rev(x) and math combination to calculate the number of nice pairs (accepted): <br />
````python
class Solution:
    def countNicePairs(self, nums: List[int]) -> int:
        D = {}
        N = len(nums)
        for i in range(N):
            d = nums[i] - int(str(nums[i])[::-1])
            if d in D:
                D[d] += 1
            else:
                D[d] = 1
        
        res = 0
        for key in D:
            res += comb(D[key], 2)

        return res % 1000000007
````

**Time Complexity** <br />
O(N)
