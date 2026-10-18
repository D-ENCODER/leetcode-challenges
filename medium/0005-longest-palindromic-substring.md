# 5. Longest Palindromic Substring

- **Difficulty:** Medium
- **LeetCode Link:** [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)
- **Topics:** `Two Pointers`, `Array`
- **Language:** Python 3

## Approach & Intuition

The core insight is to expand around each character (and each pair of characters) to find the longest palindromic substring.

- **Step**: Check if the input string is empty or has a length of 1, returning the string if true.
- **Step**: Define a helper function `expand_around_center` to find the length of the palindrome by expanding around the center.
- **Step**: Iterate through each character in the string, using the helper function to find the longest palindrome centered at that character and the one centered between that character and the next one.
- **Step**: Update the start index and maximum length of the palindrome found.
- **Step**: Return the longest palindromic substring found.

## Python 3 Solution

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        if not s or len(s) <= 1:
            return s
        start = 0
        max_len = 0
        def expand_around_center(left: int, right: int) -> int:
            while left >= 0 and right < len(s) and s[left] == s[right]:
                left -= 1
                right += 1
            return right - left - 1
        for i in range(len(s)):
            len1 = expand_around_center(i, i)
            len2 = expand_around_center(i, i + 1)
            curr_max = max(len1, len2)
            if curr_max > max_len:
                max_len = curr_max
                start = i - (curr_max - 1) // 2
        return s[start:start + max_len]
```

## Complexity Analysis

- **Time Complexity:** `O(n^2)` — The solution iterates through each character in the string and expands around it, leading to a quadratic time complexity.
- **Space Complexity:** `O(1)` — The solution uses a constant amount of extra space, regardless of the input size.
