# 7. Reverse Integer

- **Difficulty:** Medium
- **Pattern:** Math & Bit Manipulation
- **Language:** Python
- **Time Complexity:** O(log₁₀(x))
- **Space Complexity:** O(1)
- **Runtime:** 96.8% Faster
- **LeetCode Link:** [https://leetcode.com/problems/reverse-integer/](https://leetcode.com/problems/reverse-integer/)

## Approach & Notes

Popped and pushed base-10 digits while validating 32-bit signed integer bounds [-2³¹, 2³¹ - 1].

---

## Problem Statement

Given a signed 32-bit integer `x`, return `x` _with its digits reversed_. If reversing `x` causes the value to go outside the signed 32-bit integer range `[-231, 231 - 1]`, then return `0`.

**Assume the environment does not allow you to store 64-bit integers (signed or unsigned).**



**Example 1:**

```
Input: x = 123
Output: 321
```

**Example 2:**

```
Input: x = -123
Output: -321
```

**Example 3:**

```
Input: x = 120
Output: 21
```



**Constraints:**

* `-2^31 <= x <= 2^31 - 1`

---

## Solution

```python
class Solution:
    def reverse(self, x):
        ans = 0
        sign = -1 if x < 0 else 1
        x *= sign

        while x:
            ans = ans * 10 + x % 10
            x //= 10
        return 0 if ans < -2**31 or ans > 2**31 - 1 else sign * ans
```
