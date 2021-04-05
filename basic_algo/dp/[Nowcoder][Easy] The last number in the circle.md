https://www.nowcoder.com/questionTerminal/0e0aab617cf84e649622623a7ddbd6cd <br />
https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/ <br />
Josephus problem. <br />

**Algorithm:** <br />
Brute force (time limit exceeded): <br />
````python
N = int(input())
queue = [i for i in range(1, N + 1)]
i = 2 % len(queue)
while len(queue) > 1:
    queue.pop(i)
    i = (i + 2) % len(queue)
print(queue[0])
````
DP (accepted): <br />
````python
N = int(input())
f = 0
for i in range(1, N + 1):
    f = (f + 3) % i # f(n) = (f(n - 1) + 3 % n) % n
print(f + 1)
````
