# 5. Longest Palindromic Substring

- **Difficulty:** Medium
- **Pattern:** Two Pointers / Center Expansion
- **Language:** Python
- **Time Complexity:** O(n²)
- **Space Complexity:** O(1)
- **Runtime:** 95.4% Faster
- **LeetCode Link:** [https://leetcode.com/problems/longest-palindromic-substring/](https://leetcode.com/problems/longest-palindromic-substring/)

## Approach & Notes

Expanded around both odd and even palindrome centers at every index to track the maximum palindrome span.

---

## Problem Statement

Given a string `s`, return _the longest palindromic substring_ in `s`.



**Example 1:**

```
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```

**Example 2:**

```
Input: s = "cbbd"
Output: "bb"
```



**Constraints:**

* `1 <= s.length <= 1000`
* `s` consist of only digits and English letters.

---

## Solution

```python
class Solution:
    def longestPalindrome(self, s):
        if not s:
            return ''

        def extend(s, i, j):
            while i >= 0 and j < len(s):
                if s[i] != s[j]:
                    break
                i -= 1
                j += 1
            return i + 1, j - 1
        indices = [0, 0]
        for i in range(len(s)):
            l1, r1 = extend(s, i, i)
            if r1 - l1 > indices[1] - indices[0]:
                indices = l1, r1
            if i + 1 < len(s) and s[i] == s[i + 1]:
                l2, r2 = extend(s, i, i + 1)
                if r2 - l2 > indices[1] - indices[0]:
                    indices = l2, r2
        return s[indices[0]:indices[1] + 1]
```
