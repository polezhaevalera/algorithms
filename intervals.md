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
    res = []
    for interval in intervals:
        if interval[1] < newInterval[0]:
            res.append(interval)
        elif interval[0] > newInterval[1]:
            res.append(newInterval)
            newInterval = interval
        else:
            newInterval = [min(newInterval[0], interval[0]), max(newInterval[1], interval[1])]            
    res.append(newInterval)
    return res

```
