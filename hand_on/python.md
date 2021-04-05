# Python 3
### Custom sorting
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
sorted(temp, key=cmp_to_key(custom))
# output: [11, 7, 5, 3, 2]
````
Approach 2: <br />
lambda