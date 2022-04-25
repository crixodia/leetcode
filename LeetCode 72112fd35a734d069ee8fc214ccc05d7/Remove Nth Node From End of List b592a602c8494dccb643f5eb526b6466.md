# Remove Nth Node From End of List

Difficulty: Medium
Language: Python
N: 19
Related to: Linked List, Two Pointers

Given the `head` of a linked list, remove the `nth` node from the end of the list and return its head.

**Example 1:**

![https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg](https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg)

```
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]

```

**Example 2:**

```
Input: head = [1], n = 1
Output: []

```

**Example 3:**

```
Input: head = [1,2], n = 1
Output: [1]

```

**Constraints:**

- The number of nodes in the list is `sz`.
- `1 <= sz <= 30`
- `0 <= Node.val <= 100`
- `1 <= n <= sz`

Python Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def ListNode2List(self, head: Optional[ListNode]) -> List:
        l = []
        current = head
        while current:
            l.append(current.val)
            current = current.next
        return l
    
    def List2ListNode(self, l: List) -> Optional[ListNode]:
        current = head = ListNode()
        for v in l:
            current.next = ListNode(v)
            current = current.next
        return head.next
    
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        l = self.ListNode2List(head)
        l.pop(len(l) - n)
        return self.List2ListNode(l)
```

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        self.next, nodelist  = head, [self]
        while head.next:
            if len(nodelist) == n:
                nodelist.pop(0)
            nodelist += head,
            head = head.next
        nodelist[0].next = nodelist[0].next.next 
        return self.next
```