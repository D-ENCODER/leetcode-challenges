# 11. Container With Most Water

- **Difficulty:** Medium
- **Pattern:** Two Pointers
- **Language:** Python
- **Time Complexity:** O(n)
- **Space Complexity:** O(1)
- **Runtime:** 98.0% Faster
- **LeetCode Link:** [https://leetcode.com/problems/container-with-most-water/](https://leetcode.com/problems/container-with-most-water/)

## Approach & Notes

Started pointers at both ends and greedily shifted the shorter vertical line inward to maximize area.

---

## Problem Statement

You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `ith` line are `(i, 0)` and `(i, height[i])`.

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return _the maximum amount of water a container can store_.

**Notice** that you may not slant the container.

![](../.gitbook/assets/question\_11.jpg)



```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

**Example 2:**

```
Input: height = [1,1]
Output: 1
```



**Constraints:**

* `n == height.length`
* `2 <= n <= 10^5`
* `0 <= height[i] <= 10^4`

---

## Solution

```python
class Solution:
    def maxArea(self, height):
        ans = 0
        l = 0
        r = len(height) - 1
        while l < r:
            minHeight = min(height[l], height[r])
            ans = max(ans, minHeight * (r - l))
            if height[l] < height[r]:
                l += 1
            else:
                r -= 1
        return ans
```
