# 2. Add Two Numbers

- **Difficulty:** Medium
- **LeetCode Link:** [Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)
- **Topics:** `Iteration / Array`, `Array`, `Two Pointers`
- **Language:** Python 3

## Approach & Intuition

The problem can be solved by simulating the addition of two numbers digit by digit, starting from the least significant digit.

- **Step 1**: Initialize a dummy node and a current node to build the resulting linked list. - **Step 2**: Iterate through both input linked lists, adding corresponding values and the carry from the previous addition. - **Step 3**: Update the carry and create a new node with the sum's least significant digit. - **Step 4**: Move to the next nodes in the input lists and the result list until both lists are exhausted.

## Python 3 Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l1 or not l2: 
            return l1 or l2
        resultNode = ListNode(0)
        currentNode = resultNode
        carry = 0
        while l1 or l2:
            current_sum = carry
            if l1:
                current_sum += l1.val
                l1 = l1.next
            if l2:
                current_sum += l2.val
                l2 = l2.next
            currentNode.next = ListNode(current_sum % 10)
            currentNode = currentNode.next
            carry = current_sum // 10
        if carry: 
            currentNode.next = ListNode(carry)
        return resultNode.next
```

## Complexity Analysis

- **Time Complexity:** `O(max(n, m))` — The while loop iterates through the linked lists until both are exhausted, making the time complexity dependent on the length of the longer list.
- **Space Complexity:** `O(max(n, m))` — The space complexity is determined by the length of the resulting linked list, which can be as long as the longer of the two input lists.
