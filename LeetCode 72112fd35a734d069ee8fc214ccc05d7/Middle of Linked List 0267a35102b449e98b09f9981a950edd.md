# Middle of Linked List

Difficulty: Easy
Language: Python
N: 876
Related to: Linked List, Two Pointers

Given the `head` of a single linked list, return *the middle node of the linked list*.

If there are two middle nodes, return **the second middle** node.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/07/23/lc-midlist1.jpg](https://assets.leetcode.com/uploads/2021/07/23/lc-midlist1.jpg)

```
Input: head = [1,2,3,4,5]
Output: [3,4,5]
Explanation: The middle node of the list is node 3.

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/07/23/lc-midlist2.jpg](https://assets.leetcode.com/uploads/2021/07/23/lc-midlist2.jpg)

```
Input: head = [1,2,3,4,5,6]
Output: [4,5,6]
Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.

```

**Constraints:**

- The number of nodes in the list is in the range `[1, 100]`.
- `1 <= Node.val <= 100`

**Python Solution:**

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        current = head
        count = 0
        while current:
            count += 1
            current = current.next
        
        im, fm = count // 2, count / 2
        middle = im if im == int(fm) else im
        
        current = head
        count = 0
        while count < middle:
            count += 1
            current = current.next
        
        return current
```

```python
class Solution:
    def middleNode(self, head):
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        return slow
```