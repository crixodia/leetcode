# Binary Tree Paths

Difficulty: Easy
Language: Python
N: 257
Related to: Binary Tree, DFS, String, Tree

Given the `root` of a binary tree, return *all root-to-leaf paths in **any order***.

A **leaf** is a node with no children.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/03/12/paths-tree.jpg](https://assets.leetcode.com/uploads/2021/03/12/paths-tree.jpg)

```
Input: root = [1,2,3,null,5]
Output: ["1->2->5","1->3"]

```

**Example 2:**

```
Input: root = [1]
Output: ["1"]

```

**Constraints:**

- The number of nodes in the tree is in the range `[1, 100]`.
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
    def binaryTreePaths(self, root: Optional[TreeNode]) -> List[str]:
        if root:
            path = []
            if not root.left and not root.right:
                path.append(f"{root.val}")
            else:
                L = self.binaryTreePaths(root.left)
                R = self.binaryTreePaths(root.right)
                for l in L:
                    path.append(f"{root.val}->{l}")
                for r in R:
                    path.append(f"{root.val}->{r}")
            return path
        return ""
```