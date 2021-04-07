https://www.nowcoder.com/questionTerminal/0c6f76c0817e4610b8ba2bcecb8c1881 <br />
Similar to [LC_253. Meeting Rooms II](https://github.com/di-huang/CrackInterview/blob/main/basic_algo/greedy/%5BLeetcode%5D%5BMedium%5D%20253.%20Meeting%20Rooms%20II.md). <br />

**Algorithm:** <br />
Min-heap + greedy.
````python
from functools import cmp_to_key
from heapq import heapify, heappush, heappop
def custom(x, y):
    if x[0] == y[0]:
        return x[1] - y[1]
    return x[0] - y[0]

N = int(input())
X = []
for i in range(N):
    s, e = map(int, input().split())
    X.append((s, e))

X = sorted(X, key=cmp_to_key(custom))
heap = []
heapify(heap)
heappush(heap, X[0][1])

for i in range(1, len(X)):
    if X[i][0] >= heap[0]:
        heappop(heap)
    heappush(heap, X[i][1])

print(len(heap))
````