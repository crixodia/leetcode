# Intersection of Two Arrays

Difficulty: Easy
Language: Python
N: 349
Related to: Array, Binary Search, Hash Table, Sorting, Two Pointers

Given two integer arrays `nums1` and `nums2`, return *an array of their intersection*. Each element in the result must be **unique** and you may return the result in **any order**.

**Example 1:**

```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2]

```

**Example 2:**

```
Input: nums1 = [4,9,5], nums2 = [9,4,9,8,4]
Output: [9,4]
Explanation: [4,9] is also accepted.

```

**Constraints:**

- `1 <= nums1.length, nums2.length <= 1000`
- `0 <= nums1[i], nums2[i] <= 1000`

**Python Solution:**

```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        if len(nums1) < len(nums2):
            short = nums1
            long = nums2
        else:
            short = nums2
            long = nums1
            
        intersect = []
        for n in short:
            if n in long and n not in intersect:
                intersect.append(n)
        
        return intersect
```

**Python Sets Solution:**

```python
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        return list(set(nums1).intersection(set(nums2)))
```