1. [Medium]压缩算法
````python
class Solution:
    def compress(self , str):
        left = str.rfind('[')
        while left != -1:
            right = str.find(']', left)
            num, temp = str[left + 1 : right].split('|')
            str = str[:left] + int(num) * temp + str[right + 1 : ]
            left = str.rfind('[')
        return str
````

2. [Medium][逛街](https://github.com/di-huang/CrackInterview/blob/main/basic_algo/stack/%5BNowcoder%5D%5BMedium%5D%20Go%20shopping.md)

````python
class Solution:
    def findBuilding(self , heights ):
        res = [1]
        stack = [] # monotonically increasing stack
        for i in range(1, len(heights)):
            cur = heights[i - 1]
            while len(stack) > 0 and stack[-1] <= cur:
                stack.pop()
            stack.append(cur)
            res.append(len(stack) + 1)
        
        stack = []
        for i in range(len(heights) - 2, -1, -1):
            cur = heights[i + 1]
            while len(stack) > 0 and stack[-1] <= cur:
                stack.pop()
            stack.append(cur)
            res[i] += len(stack)
        return res
````

4. [Medium]假期 (题目似乎在暗示什么xD)