# ⚡ LeetCode Challenges — Algorithmic Solution Vault

[![Portfolio Live Sync](https://img.shields.io/badge/Live_Portfolio-het--joshi.web.app-6366f1?style=for-the-badge)](https://het-joshi.web.app)
[![Solved](https://img.shields.io/badge/Solved-17_Challenges-10b981?style=for-the-badge)]()
[![Language](https://img.shields.io/badge/Language-Python_3-3b82f6?style=for-the-badge)]()

Curated collection of **LeetCode algorithmic solutions**, complexity analyses, and problem-solving patterns maintained by **Het Joshi ([@D-ENCODER](https://github.com/D-ENCODER))**.

> **Live Portfolio Integration:** This repository is dynamically connected to **[het-joshi.web.app](https://het-joshi.web.app)**. Any new solution added to `easy/`, `medium/`, or `hard/` automatically appears on the live portfolio website without needing a redeploy!

---

## 📂 Repository Folder Structure

Solutions are organized into difficulty directories using a zero-padded 4-digit problem number (`XXXX-problem-slug.md`):

```text
leetcode-challenges/
├── README.md                 # Documentation, folder guide & solution index
├── TEMPLATE.md               # Copy-paste template for adding new problems
├── easy/                     # 🟢 Easy difficulty solutions
│   ├── 0001-two-sum.md
│   ├── 0009-palindrome-number.md
│   ├── 0013-roman-to-integer.md
│   └── 0014-longest-common-prefix.md
├── medium/                   # 🟡 Medium difficulty solutions
│   ├── 0002-add-two-numbers.md
│   ├── 0003-longest-substring-without-repeating-characters.md
│   ├── 0005-longest-palindromic-substring.md
│   ├── ...
│   └── 0017-letter-combinations-of-a-phone-number.md
└── hard/                     # 🔴 Hard difficulty solutions
    ├── 0004-median-of-two-sorted-arrays.md
    └── 0010-regular-expression-matching.md
```

---

## ➕ How to Add a New Solution

1. Copy [`TEMPLATE.md`](./TEMPLATE.md) into the appropriate difficulty folder (`easy/`, `medium/`, or `hard/`).
2. Name the file `XXXX-problem-slug.md` (e.g., `medium/0018-4sum.md` or even a raw code file like `medium/0018-4sum.py`).
3. Fill in the metadata bullets (`Difficulty`, `Pattern`, `Time Complexity`, `Space Complexity`), your `Approach & Notes`, and the `Solution` code block.
4. Commit and push to `main` — your portfolio at **[het-joshi.web.app](https://het-joshi.web.app)** will automatically parse the new file and update your live stats and interactive code viewer!

---

## 📊 Solved Problems Index (17 Total: 4 Easy • 11 Medium • 2 Hard)

| # | Problem Title | Difficulty | Algorithmic Pattern | Time | Space |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 0001 | [Two Sum](./easy/0001-two-sum.md) | 🟢 Easy | `Hash Map` | `O(n)` | `O(n)` |
| 0002 | [Add Two Numbers](./medium/0002-add-two-numbers.md) | 🟡 Medium | `Linked List` | `O(max(m, n))` | `O(max(m, n))` |
| 0003 | [Longest Substring Without Repeating Characters](./medium/0003-longest-substring-without-repeating-characters.md) | 🟡 Medium | `Sliding Window` | `O(n)` | `O(min(m, n))` |
| 0004 | [Median of Two Sorted Arrays](./hard/0004-median-of-two-sorted-arrays.md) | 🔴 Hard | `Binary Search` | `O(log(min(m, n)))` | `O(1)` |
| 0005 | [Longest Palindromic Substring](./medium/0005-longest-palindromic-substring.md) | 🟡 Medium | `Two Pointers / Center Expansion` | `O(n²)` | `O(1)` |
| 0006 | [Zigzag Conversion](./medium/0006-zigzag-conversion.md) | 🟡 Medium | `String / Matrix Simulation` | `O(n)` | `O(n)` |
| 0007 | [Reverse Integer](./medium/0007-reverse-integer.md) | 🟡 Medium | `Math & Bit Manipulation` | `O(log₁₀(x))` | `O(1)` |
| 0008 | [String to Integer (atoi)](./medium/0008-string-to-integer-atoi.md) | 🟡 Medium | `String Parsing / Deterministic State` | `O(n)` | `O(1)` |
| 0009 | [Palindrome Number](./easy/0009-palindrome-number.md) | 🟢 Easy | `Math` | `O(log₁₀(n))` | `O(1)` |
| 0010 | [Regular Expression Matching](./hard/0010-regular-expression-matching.md) | 🔴 Hard | `Dynamic Programming` | `O(m · n)` | `O(m · n)` |
| 0011 | [Container With Most Water](./medium/0011-container-with-most-water.md) | 🟡 Medium | `Two Pointers` | `O(n)` | `O(1)` |
| 0012 | [Integer to Roman](./medium/0012-integer-to-roman.md) | 🟡 Medium | `Greedy / Value Mapping` | `O(1)` | `O(1)` |
| 0013 | [Roman to Integer](./easy/0013-roman-to-integer.md) | 🟢 Easy | `Hash Map / Left-to-Right Pass` | `O(n)` | `O(1)` |
| 0014 | [Longest Common Prefix](./easy/0014-longest-common-prefix.md) | 🟢 Easy | `Vertical Scanning` | `O(S)` | `O(1)` |
| 0015 | [3Sum](./medium/0015-3sum.md) | 🟡 Medium | `Sorting + Two Pointers` | `O(n²)` | `O(1)` |
| 0016 | [3Sum Closest](./medium/0016-3sum-closest.md) | 🟡 Medium | `Sorting + Two Pointers` | `O(n²)` | `O(1)` |
| 0017 | [Letter Combinations of a Phone Number](./medium/0017-letter-combinations-of-a-phone-number.md) | 🟡 Medium | `Backtracking / Combinations` | `O(4ⁿ · n)` | `O(n)` |
