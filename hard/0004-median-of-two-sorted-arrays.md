# 4. Median of Two Sorted Arrays

- **Difficulty:** Hard
- **LeetCode Link:** [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/)
- **Topics:** `Sorting`, `Array`, `Two Pointers`
- **Language:** Python 3

## Approach & Intuition

The core insight is to combine both sorted arrays and find the median of the combined array.

- **Step 1**: Concatenate the two input arrays into a single array. - **Step 2**: Sort the combined array. - **Step 3**: Determine the median based on the length of the combined array, checking if it is even or odd.

## Python 3 Solution

```python
class Solution:
    def findMedianSortedArrays(self, nums1: list[int], nums2: list[int]) -> float:
        nums3 = nums1 + nums2
        nums3.sort()
        if len(nums3) % 2 == 0:
            i1 = floor(len(nums3) / 2)
            i2 = ceil(len(nums3) / 2)
            return (nums3[i1 - 1] + nums3[i2]) / 2
        else:
            return nums3[len(nums3) // 2]
```

## Complexity Analysis

- **Time Complexity:** `O((m + n) log(m + n))` — The time complexity is dominated by the sorting operation, which is O((m + n) log(m + n)), where m and n are the lengths of the two input arrays.
- **Space Complexity:** `O(m + n)` — The space complexity is O(m + n) due to the creation of a new array that combines both input arrays.
