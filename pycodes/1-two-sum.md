# leetcode 1.Two Sum

[Jump To The Questions Directory](./questions-list.md)

## Question
```
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```
## Analysis
```
给定一个包含多个整数的数组，返回两个数在数组中的位置，这两个数的和等于指定的数值

假定 只有最多一种可能且没有重复元素
遍历一遍数组，对已遍历的数值建立hash表（pyhon中可用dict），遍历到A[i]时，再hash表中查找Target-A[i],找到则返回i和hash_key


如果有多种解和有重复元素时算法上该怎么调整呢？
```

## Solution
```py
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        if not isinstance(nums,list):
            return None
        nums_hash = {}
        for i in range(len(nums)):
            t_k = target-nums[i]
            if nums_hash.get(t_k,None)!=None:
                return sorted([i,nums_hash[t_k]])
            else:
                nums_hash[nums[i]] = i
        return []
```
