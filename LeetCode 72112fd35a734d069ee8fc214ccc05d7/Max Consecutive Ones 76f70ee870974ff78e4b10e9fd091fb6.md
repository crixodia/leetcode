# Max Consecutive Ones

Difficulty: Easy
Language: Python
N: 485
Related to: Array

Given a binary array `nums`, return *the maximum number of consecutive* `1`*'s in the array*.

**Example 1:**

```
Input: nums = [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.

```

**Example 2:**

```
Input: nums = [1,0,1,1,0,1]
Output: 2

```

**Constraints:**

- `1 <= nums.length <= 105`
- `nums[i]` is either `0` or `1`.

**Python Solution:**

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        s = "".join(list(map(str, nums)))
        S = s.split("0")
        L = list(map(len, S))
        return max(L)
```