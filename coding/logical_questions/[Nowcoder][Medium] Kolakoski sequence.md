https://www.nowcoder.com/questionTerminal/79358002fe7c48a6a74f96c0dc734fa1 <br />
Similar to LC_481. Magical String: https://leetcode.com/problems/magical-string/ <br />

**Algorithm:** <br />
Find the logical pattern. <br />
````python
N, M = map(int, input().split(" "))
X = list(map(int, input().split(" ")))

i = 1
seq = [X[0]] * X[0]
while i < N:
    temp = seq[i] if i < len(seq) else X[i % M]
    seq += [X[i % M]] * temp
    i += 1

for j in range(N):
    print(seq[j])

````
