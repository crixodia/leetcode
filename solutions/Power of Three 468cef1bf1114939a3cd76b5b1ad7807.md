# Power of Three

Difficulty: Easy
Language: Python
N: 326
Related to: Math, Recursion

Given an integer `n`, return *`true` if it is a power of three. Otherwise, return `false`*.

An integer `n` is a power of three, if there exists an integer `x` such that `n == 3x`.

**Example 1:**

```
Input: n = 27
Output: true

```

**Example 2:**

```
Input: n = 0
Output: false

```

**Example 3:**

```
Input: n = 9
Output: true

```

**Constraints:**

- `231 <= n <= 231 - 1`

**Follow up:**

Could you solve it without loops/recursion?

**Python Solution:**

```python
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        if n < 1:
            return False
        from math import log, ceil, floor
        r = round(log(n)/log(3), 10)
        return ceil(r) == floor(r)
```