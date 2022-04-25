# Symmetric Tree

Difficulty: Easy
Language: Python
N: 101
Related to: BFS, Binary Tree, DFS, Tree

Given the `root` of a binary tree, *check whether it is a mirror of itself* (i.e., symmetric around its center).

**Example 1:**

![https://assets.leetcode.com/uploads/2021/02/19/symtree1.jpg](https://assets.leetcode.com/uploads/2021/02/19/symtree1.jpg)

```
Input: root = [1,2,2,3,4,4,3]
Output: true

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/02/19/symtree2.jpg](https://assets.leetcode.com/uploads/2021/02/19/symtree2.jpg)

```
Input: root = [1,2,2,null,3,null,3]
Output: false

```

**Constraints:**

- The number of nodes in the tree is in the range `[1, 1000]`.
- `100 <= Node.val <= 100`

**Follow up:**

Could you solve it both recursively and iteratively?

**Python Recursive Solution:**

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSameTreeSymmetric(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        if p is None and q is None:
            return True
        elif p is None or q is None:
            return False
        elif q.val == p.val:
            r = self.isSameTreeSymmetric(q.right, p.left)
            l = self.isSameTreeSymmetric(q.left, p.right)
            return r and l
        return False
    
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        return self.isSameTreeSymmetric(root.left, root.right)
```