# 6. Zigzag Conversion

- **Difficulty:** Medium
- **Pattern:** String / Matrix Simulation
- **Language:** Python
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
- **Runtime:** 94.7% Faster
- **LeetCode Link:** [https://leetcode.com/problems/zigzag-conversion/](https://leetcode.com/problems/zigzag-conversion/)

## Approach & Notes

Traversed characters with a directional step (+1 / -1) across numRows row buffers before joining.

---

## Problem Statement

The string `"PAYPALISHIRING"` is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

```
P   A   H   N
A P L S I I G
Y   I   R
```

And then read line by line: `"PAHNAPLSIIGYIR"`

Write the code that will take a string and make this conversion given a number of rows:

```
string convert(string s, int numRows);
```



**Example 1:**

```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

**Example 2:**

```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:
P     I    N
A   L S  I G
Y A   H R
P     I
```

**Example 3:**

```
Input: s = "A", numRows = 1
Output: "A"
```



**Constraints:**

* `1 <= s.length <= 1000`
* `s` consists of English letters (lower-case and upper-case), `','` and `'.'`.
* `1 <= numRows <= 1000`

---

## Solution

```python
class Solution:
    def convert(self, s, numRows):
        rows = [''] * numRows
        k = 0
        direction = (numRows == 1) - 1
        for c in s:
            rows[k] += c
            if k == 0 or k == numRows - 1:
                direction *= -1
            k += direction
        return ''.join(rows)
```
