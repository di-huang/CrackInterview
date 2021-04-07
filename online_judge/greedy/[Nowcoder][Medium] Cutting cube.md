https://www.nowcoder.com/questionTerminal/29f9a255e8964bb0a097b5c125543dd8 <br />

**Algorithm:** <br />
Greedy + AM–GM inequality.
````python
x, y, z, k = map(int, input().split())
x, y, z = sorted([x - 1, y - 1, z - 1])
x = min(k // 3, x)
y = min((k - x) // 2, y)
z = min((k - x - y), z)
print((x + 1) * (y + 1) * (z + 1))
````
Alternative: <br />
````python
from math import ceil
x, y, z, k = map(int, input().split())
x, y, z = sorted([x - 1, y - 1, z - 1])
x = min(ceil(k / 3), x)
y = min(ceil((k - x) / 2), y)
z = min((k - x - y), z)
print((x + 1) * (y + 1) * (z + 1))
````