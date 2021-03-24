https://leetcode.com/problems/queue-reconstruction-by-height/

**Algorithm:** <br />
1. Sort the array of people by the following rule: <br />
height matters most, for example, [7, 0] > [5, 0] <br />
k value matters secondly, for example, [7, 0] > [7, 1] <br />
2. Go through the sorted array of people and insert each element into the corresponding position of the result <br />
For example, insert [7, 1] into the 1st position of the result <br />
and insert [5, 2] into the 2nd position of the result... <br />


**Time Complexity** <br />
O(n^2)
