# Convert Sorted Array to Binary Search Tree

Difficulty: Easy
Language: Python
N: 108
Related to: Array, BST, Binary Tree, Divide and Conquer, Tree

Given an integer array `nums` where the elements are sorted in **ascending order**, convert *it to a **height-balanced** binary search tree*.

A **height-balanced** binary tree is a binary tree in which the depth of the two subtrees of every node never differs by more than one.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/02/18/btree1.jpg](https://assets.leetcode.com/uploads/2021/02/18/btree1.jpg)

```
Input: nums = [-10,-3,0,5,9]
Output: [0,-3,9,-10,null,5]
Explanation: [0,-10,5,null,-3,null,9] is also accepted:

```

![https://assets.leetcode.com/uploads/2021/02/18/btree2.jpg](https://assets.leetcode.com/uploads/2021/02/18/btree2.jpg)

**Example 2:**

![https://assets.leetcode.com/uploads/2021/02/18/btree.jpg](https://assets.leetcode.com/uploads/2021/02/18/btree.jpg)

```
Input: nums = [1,3]
Output: [3,1]
Explanation: [1,3] and [3,1] are both a height-balanced BSTs.

```

**Constraints:**

- `1 <= nums.length <= 104`
- `104 <= nums[i] <= 104`
- `nums` is sorted in a **strictly increasing** order.

**Python Solution:**

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        n = len(nums)
        if n > 0:
            node = TreeNode(nums[n//2])
            node.left = self.sortedArrayToBST(nums[:n//2])
            node.right = self.sortedArrayToBST(nums[(n//2)+1:])
            return node
```