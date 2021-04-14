https://www.nowcoder.com/questionTerminal/7cd9a140387e455a972e8fea0e74be2c

**Algorithm:** <br />
Backtracking (time limit exceeded): <br />
````python
class Solution:
    def __init__(self, N, work, gym):
        self.count = 0
        self.res = 100000
        self.N = N
        self.work = work
        self.gym = gym
        self.stack = []

    def solve(self):
        self.helper(0)
        return self.res

    def helper(self, idx):
        if idx == self.N:
            self.res = min(self.res, self.count)
            return

        if self.work[idx] == 1:
            if len(self.stack) == 0 or self.stack[-1] != 1:
                self.stack.append(1)
                self.helper(idx + 1)
                self.stack.pop()

        if self.gym[idx] == 1:
            if len(self.stack) == 0 or self.stack[-1] != 2:
                self.stack.append(2)
                self.helper(idx + 1)
                self.stack.pop()
        
        self.count += 1
        self.stack.append(0)
        self.helper(idx + 1)
        self.stack.pop()
        self.count -= 1

N = int(input())
work = list(map(int, input().split(" ")))
gym = list(map(int, input().split(" ")))
sol = Solution(N, work, gym)
print(sol.solve())
````

Greedy (doesn't work well): <br />
````python
N = int(input())
work = list(map(int, input().split(" ")))
gym = list(map(int, input().split(" ")))
done, res = 0, 0

for i in range(N):
    if work[i] == 1 and gym[i] == 0 and done != 1:
        done = 1
    elif work[i] == 0 and gym[i] == 1 and done != 2:
        done = 2
    elif work[i] == 1 and gym[i] == 1:
        if done == 1:
            done = 2
        elif done == 2:
            done = 1
        else:
            if i + 1 < N and work[i + 1] == 1:
                done = 2
            else:
                done = 1
    else:
        done = 0
        res += 1

print(res)
````

DP (accepted): <br />
Approach 1: <br />
````python
N = int(input())
work = list(map(int, input().split(" ")))
gym = list(map(int, input().split(" ")))
dp = [[0] * 3 for i in range(N)]
dp[0] = [0, work[0], gym[0]]

for i in range(1, N):
    if work[i] == 1:
        dp[i][1] = 1 + max(dp[i - 1][0], dp[i - 1][2])
    if gym[i] == 1:
        dp[i][2] = 1 + max(dp[i - 1][0], dp[i - 1][1])
    dp[i][0] = max(dp[i - 1][0], dp[i - 1][1], dp[i - 1][2])

print(N - max(dp[-1][0], dp[-1][1], dp[-1][2]))
````
Approach 2: <br />
````python
N = int(input())
work = list(map(int, input().split(" ")))
gym = list(map(int, input().split(" ")))
dp = [[100000] * 3 for i in range(N)]
dp[0] = [1, 1 - work[0], 1 - gym[0]]

for i in range(1, N):
    if work[i] == 1:
        dp[i][1] = min(dp[i - 1][0], dp[i - 1][2])
    if gym[i] == 1:
        dp[i][2] = min(dp[i - 1][0], dp[i - 1][1])
    dp[i][0] = 1 + min(dp[i - 1][0], dp[i - 1][1], dp[i - 1][2])

print(min(dp[-1][0], dp[-1][1], dp[-1][2]))
````
