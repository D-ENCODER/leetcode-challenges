# 3. Longest Substring Without Repeating Characters

- **Difficulty:** Medium
- **LeetCode Link:** [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
- **Topics:** `Hash Table`, `Two Pointers`, `Array`
- **Language:** Python 3

## Approach & Intuition

Maintain a sliding window that expands and contracts to ensure no repeating characters are present.

- **Step**: Initialize a hash map to track the last index of each character, and variables to track the start of the current window and the maximum length of the substring without repeating characters. 
- **Step**: Iterate through the string, updating the start of the window if a repeating character is found and updating the hash map with the current character's index. 
- **Step**: Calculate the length of the current window and update the maximum length if the current window is larger. 
- **Step**: Return the maximum length of the substring without repeating characters.

## Python 3 Solution

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        char_map = {}
        left = 0
        max_len = 0
        for right, char in enumerate(s):
            if char in char_map and char_map[char] >= left:
                left = char_map[char] + 1
            char_map[char] = right
            max_len = max(max_len, right - left + 1)
        return max_len
```

## Complexity Analysis

- **Time Complexity:** `O(n)` — The solution uses a single loop that iterates through the string once, making the time complexity linear with respect to the length of the string.
- **Space Complexity:** `O(min(n, m))` — The hash map stores characters and their indices, with a maximum size of the number of unique characters in the string, which is bounded by the size of the character set (m).
