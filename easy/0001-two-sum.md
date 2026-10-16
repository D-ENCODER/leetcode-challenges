# 1. Two Sum

- **Difficulty:** Easy
- **Pattern:** Hash Map
- **Language:** Python
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
- **Runtime:** 98.4% Faster
- **LeetCode Link:** [https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/two-sum/)

## Approach & Notes

Single-pass hash table storing seen elements and their indices to resolve target complements in O(1) lookup time.

---

## Problem Statement

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have _**exactly**_** one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```
Input: nums = [3,3], target = 6
Output: [0,1]
```



**Constraints:**

* `2 <= nums.length <= 10^4`
* `-10^9 <= nums[i] <= 10^9`
* `-10^9 <= target <= 10^9`
* **Only one valid answer exists.**

**Follow-up:** Can you come up with an algorithm that is less than `O(n2)` time complexity?

---

## Solution

```python
class Solution:
    def twoSum(self, nums, target):
        seen = {}
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in seen:
                return seen[complement], i
            seen[nums[i]] = i
```
