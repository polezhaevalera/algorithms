# arrays
+[Two sum](#two-sum)
+[3sum](#3sum)
+[Subarray sum equals k](#subarray-sum-equals-k)

## Two sum

https://leetcode.com/problems/two-sum/

## 3sum

https://leetcode.com/problems/3sum/

```python
def threeSum(self, nums: List[int]) -> List[List[int]]:
    nums.sort()
    result = []
    for first in range(len(nums)-2):
        if first > 0 and nums[first] == nums[first-1]:
            continue
        second = first+1
        third = len(nums) - 1
        while second < third:
            sum = nums[first] + nums[second] + nums[third]
            if sum < 0:
                second = second + 1
            elif sum > 0:
                third = third - 1
            else:
                result.append([nums[first], nums[second], nums[third]])
                while second < third and nums[second] == nums[second+1]:
                    second = second + 1
                while third > second and nums[third] == nums[third-1]:
                    third = third - 1
                second = second + 1
                third = third - 1
    return result
 ```
    

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
