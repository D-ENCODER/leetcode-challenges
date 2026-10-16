# 3. Longest Substring Without Repeating Characters

- **Difficulty:** Medium
- **Pattern:** Sliding Window
- **Language:** Python
- **Time Complexity:** O(n)
- **Space Complexity:** O(min(m, n))
- **Runtime:** 97.8% Faster
- **LeetCode Link:** [https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

## Approach & Notes

Maintained a dynamic sliding window [l, r] with a frequency counter to contract left pointer upon duplicate characters.

---

## Problem Statement

Given a string `s`, find the length of the **longest substring** without repeating characters.

**Example 1:**

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

**Example 2:**

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

**Example 3:**

```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

**Constraints:**

* `0 <= s.length <= 5 * 104`
* `s` consists of English letters, digits, symbols and spaces.

---

## Solution

```python
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        ans = 0
        count = Counter()
        l = 0
        for r, c in enumerate(s):
            count[c] += 1
            while count[c] > 1:
                count[s[l]] -= 1
                l += 1
            ans = max(ans, r - l + 1)
        return ans
```
