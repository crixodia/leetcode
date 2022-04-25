# Contains Duplicate

Difficulty: Easy
Language: Python
N: 217
Related to: Array, Hash Table, Sorting

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

```
Input: nums = [1,2,3,1]
Output: true

```

**Example 2:**

```
Input: nums = [1,2,3,4]
Output: false

```

**Example 3:**

```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true

```

**Constraints:**

- `1 <= nums.length <= 105`
- `109 <= nums[i] <= 109`

**Python Solution:**

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        n = len(nums)
        i = 0
        j = 1
        while j < n:
            if nums[i] == nums[j]:
                return True
            i = i + 1
            j = j + 1
        return False
```

<aside>
💡 It is possible to solve it using merge sort and asking for duplicates during sorting.

</aside>