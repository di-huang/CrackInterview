https://leetcode.com/problems/remove-nth-node-from-end-of-list/ <br />
The difficulty of this one should have been set to easy. <br />

**Algorithm:** <br />
Use faster and slower pointers. Faster pointer moves forward n steps in advance. Note that we need to set a head0 to the parent of head so that we can remove the head conveniently. Also, use **faster.next != null** as the termination condition of the while loop. <br />

**Time Complexity** <br />
O(list.size)
