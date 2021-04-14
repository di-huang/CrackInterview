https://leetcode-cn.com/problems/increasing-subsequences/ <br />

**Algorithm:** <br />
Standard DFS question. <br />
````python
class Solution:
    def findSubsequences(self, nums: List[int]) -> List[List[int]]:
        def dfs(idx, nums, tmp, res):   
            if idx >= len(nums):
                if len(tmp) >= 2:
                    res.append(list(tmp))
                return
                
            if not tmp or nums[idx] >= tmp[-1]:
                tmp.append(nums[idx])
                dfs(idx + 1, nums, tmp, res)
                tmp.pop()
            
            if not tmp or nums[idx] != tmp[-1]:
                dfs(idx + 1, nums, tmp, res)

        tmp, res = [], []
        dfs(0, nums, tmp, res)
        return res
````
