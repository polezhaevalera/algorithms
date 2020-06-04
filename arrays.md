# arrays
+[Two sum](#two-sum)
+[3sum](#3sum)
+[Subarray sum equals k](#subarray-sum-equals-k)

## Two sum

https://leetcode.com/problems/two-sum/

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    nums = [elem for elem in enumerate(nums)]
    nums.sort(key=lambda x: x[1])
    first = 0
    last = len(nums) - 1
    while first != last:
        if nums[first][1] + nums[last][1] == target:
            return [nums[first][0], nums[last][0]]
        elif nums[first][1] + nums[last][1] < target:
            first = first + 1
        else:
            last = last - 1

```

## 3sum

https://leetcode.com/problems/3sum/

## Subarray sum equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python
def subarraySum(self, nums, k):
    count = 0
    sums = 0
    d = dict()
    d[0] = 1
    for i in range(len(nums)):
        sums += nums[i]
        count += d.get(sums - k, 0)
        d[sums] = d.get(sums, 0)+1
    return(count)
```
