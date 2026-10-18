# 1. Two Sum

- **Difficulty:** Easy
- **LeetCode Link:** [Two Sum](https://leetcode.com/problems/two-sum/)
- **Topics:** `Hash Table`, `Array`, `Two Pointers`
- **Language:** Python 3

## Approach & Intuition

By storing each number's index in a hash map as we iterate through the list, we can quickly check if the complement of the current number (to reach the target sum) has already been seen.

- **Step**: Initialize an empty hash map to store numbers and their indices.
- **Step**: Iterate through the list of numbers, for each number calculate its complement with respect to the target.
- **Step**: Check if the complement exists in the hash map; if it does, return the indices of the complement and the current number.
- **Step**: If the complement does not exist, store the current number and its index in the hash map.

## Python 3 Solution

```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        seen = {} 
        for index, num in enumerate(nums):
            complement = target - num
            if complement in seen:
                return [seen[complement], index]
            seen[num] = index
        return []
```

## Complexity Analysis

- **Time Complexity:** `O(n)` — The solution iterates through the list of numbers exactly once, performing constant-time operations for each element.
- **Space Complexity:** `O(n)` — A hash map is used to store up to n elements, where n is the number of elements in the input list.
