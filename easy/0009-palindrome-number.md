# 9. Palindrome Number

- **Difficulty:** Easy
- **Pattern:** Math
- **Language:** Python
- **Time Complexity:** O(log₁₀(n))
- **Space Complexity:** O(1)
- **Runtime:** 97.3% Faster
- **LeetCode Link:** [https://leetcode.com/problems/palindrome-number/](https://leetcode.com/problems/palindrome-number/)

## Approach & Notes

Reversed the integer digits mathematically without string conversion overhead and compared against original.

---

## Problem Statement

Given an integer `x`, return `true` if `x` is palindrome integer.

An integer is a **palindrome** when it reads the same backward as forward.

* For example, `121` is a palindrome while `123` is not.



**Example 1:**

```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

**Example 2:**

```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

**Example 3:**

```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```



**Constraints:**

* `-2^31 <= x <= 2^31 - 1`



**Follow up:** Could you solve it without converting the integer to a string?

---

## Solution

```python
class Solution:
    def isPalindrome(self,x):
        if x < 0:
            return False
        rev = 0
        y = x
        while y:
            rev = rev * 10 + y % 10
            y //= 10
        return rev == x
```
