1. [Easy]编译依赖问题
https://www.nowcoder.com/questionTerminal/74d0c1b6bb5a403a84093d0ffdc58ee2 <br />
````python
class Solution:
    def compileSeq(self , input ):
        input = input.split(',')
        N = len(input)
        i = 0
        s = set()
        res = []

        while len(s) < N and i < N:
            si = str(i)
            if si not in s:
                if input[i] == "-1" or input[i] in s:
                    res.append(si)
                    s.add(si)
                    i = 0
                    continue
            i += 1

        return ",".join(res)
````

2. [Easy]回文字符串
https://www.nowcoder.com/questionTerminal/1e83935468034136b201760128e49fa7 <br />
````python
X = input()
res = "false"

def is_palin(S, idx):
    if idx == 0:
        i, j = 1, len(S) - 1
    elif idx == len(S) - 1:
        i, j = 0, len(S) - 2
    else:
        i, j = 0, len(S) - 1

    while i < j:
        if S[i] != S[j]:
            return False
        if i + 1 == idx:
            i += 2
            j -= 1
        elif j - 1 == idx:
            i += 1
            j -= 2
        else:
            i += 1
            j -= 1
    
    return True

for i in range(len(X)):
    if is_palin(X, i):
        res = X[:i] + X[i + 1 :]
        break

print(res)
````

3. [Medium]游戏地图路径
https://www.nowcoder.com/questionTerminal/a4b7f297ad0e46a0a1fbac4d2da83a63 <br />
Solved by BFS. <br />
````python
N = int(input())
sy, sx, ey, ex = map(int, input().split())
M = []
for i in range(N):
    M.append(list(input()))
visited = [[False for i in range(N)] for j in range(N)]
res = -1

def is_valid(x, y):
    return M[x][y] != '#' and M[x][y] != '@' and not visited[x][y]

queue = [(sx, sy, 0)]
visited[sx][sy] = True
while len(queue) != 0:
    loc = queue.pop(0)
    x, y, d = loc[0], loc[1], loc[2]
    if x == ex and y == ey:
        res = d
        break

    if x - 1 >= 0 and is_valid(x - 1, y):
        visited[x - 1][y] = True
        queue.append((x - 1, y, d + 1))
    if x + 1 < N and is_valid(x + 1, y):
        visited[x + 1][y] = True
        queue.append((x + 1, y, d + 1))
    if y - 1 >= 0 and is_valid(x, y - 1):
        visited[x][y - 1] = True
        queue.append((x, y - 1, d + 1))
    if y + 1 < N and is_valid(x, y + 1):
        visited[x][y + 1] = True
        queue.append((x, y + 1, d + 1))

print(res)
````

