https://leetcode.com/problems/linked-list-cycle-ii/ <br />
Space complexity is limited to O(1) for this question. <br />

**Algorithm:** <br />
1. Slow and fast (2x speed) pointers => the meeting point <br />
2. One starts from the meeting point, another starts from the head. Where they meet would be the answer. <br />

**Proof:**  <br />
![alt text](https://github.com/di-huang/CrackInterview/blob/main/resource/2.jpg)
