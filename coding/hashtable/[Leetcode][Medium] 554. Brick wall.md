https://leetcode.com/problems/brick-wall/

**Algorithm:** <br />
Actually, we just need to find the gap or edge with the largest amount. A hashmap is needed to record the number of edges and we update max_edge at the same time. Return (wall.height - max_edge).

**Time Complexity** <br />
O(wall.size)
