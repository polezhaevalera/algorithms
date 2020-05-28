# intervals
+[Insert interval](#insert-interval)
+[Merge intervals](#merge-intervals)
+[Non-overlapping Intervals](#non-overlapping-intervals)

## non-overlapping intervals

https://leetcode.com/problems/non-overlapping-intervals/

```python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    if not intervals:
        return 0
    numNonOverlapping = 1
    intervals.sort(key=lambda x: x[1])
    endHolder = intervals[0][1]
    for interval in intervals:
        if interval[0] >= endHolder:
            numNonOverlapping += 1
            endHolder = interval[1]
    return len(intervals) - numNonOverlapping

```

## merge intervals

https://leetcode.com/problems/merge-intervals/

## insert interval

https://leetcode.com/problems/insert-interval/
```python
def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
    if not intervals:
        return [newInterval]
    start = newInterval[0]
    end = newInterval[1]
    left = 0
    right = len(intervals) - 1
    if intervals[right][1] < start:
        intervals.append(newInterval)
        return intervals
    while left <= right:
        mid = left + (right - left) // 2
        if intervals[mid][1] < start:
            left = mid + 1
        elif intervals[mid][0] > end:
            right = mid - 1
        elif intervals[left][1] < start:
            left += 1
        elif intervals[right][0] > end:
            right -= 1
        else:
            start = min(start, intervals[left][0])
            end = max(end, intervals[right][1])
            break
    return intervals[:left] + [[start, end]] + intervals[right+1:]

```
