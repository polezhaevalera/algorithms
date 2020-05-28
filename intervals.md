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

```python
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    intervals.sort()
    int_current = 0
    lenght_int = len(intervals)
    results = []
    while(int_current < lenght_int):
        start = intervals[int_current][0]
        end = intervals[int_current][1]
        while(int_current < lenght_int-1 and intervals[int_current+1][0] <= end):
            end = max(end, intervals[int_current+1][1])
            int_current += 1
        results.append([start, end])
        int_current += 1
        return results


## insert interval

https://leetcode.com/problems/insert-interval/
