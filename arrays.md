# arrays
+[Two sum](#two-sum)
+[3sum](#3sum)
+[Subarray sum equals k](#subarray-sum-equals-k)

## Two sum

https://leetcode.com/problems/two-sum/

```python
def twoSum(self, nums, target):
    index_dict = {}
    for i in range(len(nums)):
        if nums[i] in index_dict:
            return [index_dict[nums[i]], i]
        index_dict[target - nums[i]] = i

```

## 3sum

https://leetcode.com/problems/3sum/

## Subarray sum equals k

https://leetcode.com/problems/subarray-sum-equals-k/
