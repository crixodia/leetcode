# Invert Binary Tree

Difficulty: Easy
Language: Python
N: 226
Related to: BFS, Binary Tree, DFS, Tree

Given the `root` of a binary tree, invert the tree, and return *its root*.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/03/14/invert1-tree.jpg](https://assets.leetcode.com/uploads/2021/03/14/invert1-tree.jpg)

```
Input: root = [4,2,7,1,3,6,9]
Output: [4,7,2,9,6,3,1]

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/03/14/invert2-tree.jpg](https://assets.leetcode.com/uploads/2021/03/14/invert2-tree.jpg)

```
Input: root = [2,1,3]
Output: [2,3,1]

```

**Example 3:**

```
Input: root = []
Output: []

```

**Constraints:**

- The number of nodes in the tree is in the range `[0, 100]`.
- `100 <= Node.val <= 100`

**Python Solution:**

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        head = root
        if head:
            head.left, head.right = head.right, head.left
            self.invertTree(head.left)
            self.invertTree(head.right)
        return head
```