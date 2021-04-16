https://leetcode-cn.com/problems/4sum/ <br />

**Algorithm:** <br />
Basically it's very similar to the 3sum problem. The only difference is we need double outer loops instead for this question. This approach can apply to n-sum problem. <br />
````python
class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        N = len(nums)
        if N < 4:
            return []

        nums = sorted(nums)
        res = []
        for i in range(N - 3):
            if i > 0 and nums[i] == nums[i - 1]:
                continue
            for j in range(i + 1, N - 2):
                if j > i + 1 and nums[j] == nums[j - 1]:
                    continue
                l = j + 1
                r = N - 1
                while l < r:
                    if nums[i] + nums[j] + nums[l] + nums[r] == target:
                        res.append([nums[i], nums[j], nums[l], nums[r]])
                        while l < r and nums[l + 1] == nums[l]:
                            l += 1
                        while l < r and nums[r - 1] == nums[r]:
                            r -= 1
                        l += 1
                        r -= 1
                    elif nums[i] + nums[j] + nums[l] + nums[r] > target:
                        r -= 1
                    else:
                        l += 1
            
        return res
````

**Time Complexity** <br />
O(N^3)
