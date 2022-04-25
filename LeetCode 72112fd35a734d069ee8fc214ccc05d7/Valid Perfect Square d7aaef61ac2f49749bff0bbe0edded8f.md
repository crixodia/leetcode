# Valid Perfect Square

Difficulty: Easy
Language: Python
N: 367
Related to: Binary Search, Math

Given a **positive** integer *num*, write a function which returns True if *num* is a perfect square else False.

**Follow up:** **Do not** use any built-in library function such as `sqrt`.

**Example 1:**

```
Input: num = 16
Output: true

```

**Example 2:**

```
Input: num = 14
Output: false

```

**Constraints:**

- `1 <= num <= 2^31 - 1`

**Python Solution:**

```python
class Solution:
    def isPerfectSquare(self, num: int) -> bool:
        if num == 0:
            return True
        
        def nr_sr(x, x_last, a, e = 1e-10):
            x_next = (x+a/x)/2
            if abs(x_last - x_next) < e:
                return x_next
            return nr_sr(x_next, x, a, e)
        
        r = int(nr_sr(num/2, 0, num))
        return r * r == num
```