# 16. 3Sum Closest

- **Difficulty:** Medium
- **Pattern:** Sorting + Two Pointers
- **Language:** Python
- **Time Complexity:** O(n²)
- **Space Complexity:** O(1)
- **Runtime:** 95.2% Faster
- **LeetCode Link:** [https://leetcode.com/problems/3sum-closest/](https://leetcode.com/problems/3sum-closest/)

## Approach & Notes

Sorted input array and used a two-pointer sweep for each anchor index to minimize |sum - target|.

---

## Problem Statement

Given an integer array `nums` of length `n` and an integer `target`, find three integers in `nums` such that the sum is closest to `target`.

Return _the sum of the three integers_.

You may assume that each input would have exactly one solution.



**Example 1:**

<pre><code><strong>Input: nums = [-1,2,1,-4], target = 1
</strong><strong>Output: 2
</strong><strong>Explanation: The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
</strong></code></pre>

**Example 2:**

<pre><code><strong>Input: nums = [0,0,0], target = 1
</strong><strong>Output: 0
</strong><strong>Explanation: The sum that is closest to the target is 0. (0 + 0 + 0 = 0).
</strong></code></pre>



**Constraints:**

* `3 <= nums.length <= 500`
* `-1000 <= nums[i] <= 1000`
* `-104 <= target <= 104`

---

## Solution

```python
class Solution(object):
    def threeSumClosest(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        nums.sort()
        n= len(nums)
        res = float("inf")
        for i in range(n-2):
            l,r = i+1,len(nums)-1
            s1 = nums[i] + nums[i+1] + nums[i+2]
            s2 = nums[i] + nums[n-1] + nums[n-2]
            res = min([s1,s2,res], key = lambda x: abs(x-target))
            if s1 <= target <= s2:
                while l < r:
                    s = nums[i] + nums[l] + nums[r]
                    res = min([s, res], key=lambda x:abs(x-target))
                    if s < target:
                        l+=1
                    elif s > target:
                        r-=1
                    else:
                        return target
        return res
```
