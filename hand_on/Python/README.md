# Python 3
#### Custom sorting
Approach 1: <br />
````python
from functools import cmp_to_key

def custom(x, y):
    if x > y:
        return -1
    elif x < y:
    	return 1
    else:
        return 0

temp = [2,7,3,11,5]
temp = sorted(temp, key=cmp_to_key(custom))
print(temp)
# output: [11, 7, 5, 3, 2]
# Other approaches: lambda and setting parameters
````

#### String
````python
# Find index
s = "abcabc"
print(s.index('a'))
print(s.rindex('a'))
# output: 0, 3
````