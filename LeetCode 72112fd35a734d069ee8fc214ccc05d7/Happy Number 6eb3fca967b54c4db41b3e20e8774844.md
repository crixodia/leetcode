# Happy Number

Difficulty: Easy
Language: Python
N: 202
Related to: Hash Table, Math, Two Pointers

Write an algorithm to determine if a number `n` is happy.

A **happy number** is a number defined by the following process:

- Starting with any positive integer, replace the number by the sum of the squares of its digits.
- Repeat the process until the number equals 1 (where it will stay), or it **loops endlessly in a cycle** which does not include 1.
- Those numbers for which this process **ends in 1** are happy.

Return `true` *if* `n` *is a happy number, and* `false` *if not*.

**Example 1:**

```
Input: n = 19
Output: true
Explanation:
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1

```

**Example 2:**

```
Input: n = 2
Output: false

```

**Constraints:**

- `1 <= n <= 231 - 1`

**Python Solution:**

```python
class Solution:
    def isHappy(self, n: int) -> bool:
        last = n
        i = 0
        while i < 8:
            num = str(last)
            s = 0
            for c in num:
                s += int(c)*int(c)
            if s == 1:
                return True
            last = s
            i = i + 1
        return False
```