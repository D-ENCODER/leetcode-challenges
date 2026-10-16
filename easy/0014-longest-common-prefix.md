# 14. Longest Common Prefix

- **Difficulty:** Easy
- **Pattern:** Vertical Scanning
- **Language:** Python
- **Time Complexity:** O(S)
- **Space Complexity:** O(1)
- **Runtime:** 97.2% Faster
- **LeetCode Link:** [https://leetcode.com/problems/longest-common-prefix/](https://leetcode.com/problems/longest-common-prefix/)

## Approach & Notes

Compared characters column-by-column across all strings until the first mismatch or shortest string end.

---

## Problem Statement

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.



**Example 1:**

```
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```



**Constraints:**

* `1 <= strs.length <= 200`
* `0 <= strs[i].length <= 200`
* `strs[i]` consists of only lower-case English letters.

---

## Solution

```python
class Solution:
    def longestCommonPrefix(self, strs):
        if not strs:
            return ''
        for i in range(len(strs[0])):
            for j in range(1, len(strs)):
                if i == len(strs[j]) or strs[j][i] != strs[0][i]:
                    return strs[0][:i]
        return strs[0]
```
