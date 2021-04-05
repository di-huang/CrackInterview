https://leetcode.com/problems/meeting-rooms-ii/

**Algorithm:** <br />
Min-heap + greedy.
````python
class Solution:
    def custom(self, x, y):
        if x[0] == y[0]:
            return x[1] - y[1]
        return x[0] - y[0]

    def minMeetingRooms(self, intervals: List[List[int]]) -> int:
        intervals = sorted(intervals, key=cmp_to_key(self.custom))
        heap = []
        heapify(heap)
        heappush(heap, intervals[0][1])
        for i in range(1, len(intervals)):
            if intervals[i][0] >= heap[0]:
                heappop(heap)
            heappush(heap, intervals[i][1])
        return len(heap)
````