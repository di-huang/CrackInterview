https://www.nowcoder.com/questionTerminal/c0803540c94848baac03096745b55b9b <br />
字节跳动2019春招 (ByteDance, TikTok, 2019) <br />
````
1. Choose 3 out of N positions;
2. The distance between the two furthest positions is not bigger than D.
3. Return the number of combinations (mod 99997867 in the end).

1 ≤ N ≤ 1000000;
1 ≤ D ≤ 1000000;
0 ≤ position ≤ 1000000;
Position list is sorted in ascending order.

Example:
D = 3, N = 4
Position list = [1 2 3 4]
-------
Output = 4
Explain: (1, 2, 3), (1, 2, 4), (1, 3, 4), (2, 3, 4)

````

**Algorithm:** <br />
Wrong solution for counter-example (using sliding window + math combination): <br />
````python
from math import comb

N, D = map(int, input().split())
X = list(map(int, input().split()))
i, j, res = 0, 2, 0

while j < N:
    if j - i < 2:
        j += 1
    else:
        while j < N and X[j] - X[i] <= D:
            j += 1
        if j - i >= 3 and X[j - 1] - X[i] <= D:
            res += comb(j - i, 3)
        i += 1

print(res % 99997867)
````

Correct solution (using math combination): <br />
````python
from math import comb

N, D = map(int, input().split())
X = list(map(int, input().split()))
i, j, res = 0, 2, 0

while i + 2 < N:
    while j < N and X[j] - X[i] <= D:
        j += 1
    if j - i >= 3:
        res += comb(j - i - 1, 2)
    i += 1

print(res % 99997867)
````

Example input and expected output: <br />
````
6 8
2 3 5 8 10 12
--------
out: 13
wrong out: 18
(i j): (0 5, 1 5, 2 6)
Double counted (i=1, j=5) and (5 8 10) for (i=2, j=6)
````
