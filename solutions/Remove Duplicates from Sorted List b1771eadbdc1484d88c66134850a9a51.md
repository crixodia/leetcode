# Remove Duplicates from Sorted List

Difficulty: Easy
Language: Python
N: 83
Related to: Linked List

Given the `head` of a sorted linked list, *delete all duplicates such that each element appears only once*. Return *the linked list **sorted** as well*.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/01/04/list1.jpg](https://assets.leetcode.com/uploads/2021/01/04/list1.jpg)

```
Input: head = [1,1,2]
Output: [1,2]

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/01/04/list2.jpg](https://assets.leetcode.com/uploads/2021/01/04/list2.jpg)

```
Input: head = [1,1,2,3,3]
Output: [1,2,3]

```

**Constraints:**

- The number of nodes in the list is in the range `[0, 300]`.
- `100 <= Node.val <= 100`
- The list is guaranteed to be **sorted** in ascending order.

**Python Solution:**

```jsx
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        
        node = head
        if node.val == node.next.val:
            node = node.next
            node = self.deleteDuplicates(node)
        else:
            node.next = self.deleteDuplicates(node.next)
        return node
```