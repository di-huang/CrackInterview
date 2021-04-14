https://www.nowcoder.com/questionTerminal/58ae39f4436b44d9836fc89542d67f71 <br />

**Algorithm:** <br />
Brute force (time limit exceeded): <br />
````python
class Solution:
    def findBuilding(self , heights):
        res = []
        for i in range(len(heights)):
            count, Max = 1, 0
            for left in range(i - 1, -1, -1):
                if heights[left] > Max:
                    Max = max(Max, heights[left])
                    count += 1
            
            Max = 0
            for right in range(i + 1, len(heights)):
                if heights[right] > Max:
                    Max = max(Max, heights[right])
                    count += 1
            
            res.append(count)
        return res
````

Monotonic stack (accepted). <br />
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
