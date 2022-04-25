# Arranging Coins

Difficulty: Easy
Language: Python
N: 441
Related to: Binary Search, Math

You have `n` coins and you want to build a staircase with these coins. The staircase consists of `k` rows where the `ith` row has exactly `i` coins. The last row of the staircase **may be** incomplete.

Given the integer `n`, return *the number of **complete rows** of the staircase you will build*.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/04/09/arrangecoins1-grid.jpg](https://assets.leetcode.com/uploads/2021/04/09/arrangecoins1-grid.jpg)

```
Input: n = 5
Output: 2
Explanation: Because the 3rd row is incomplete, we return 2.

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/04/09/arrangecoins2-grid.jpg](https://assets.leetcode.com/uploads/2021/04/09/arrangecoins2-grid.jpg)

```
Input: n = 8
Output: 3
Explanation: Because the 4th row is incomplete, we return 3.

```

**Constraints:**

- `1 <= n <= 231 - 1`

**Python Solution:**

```python
class Solution:
    def arrangeCoins(self, n: int) -> int:
        i = 0
        while n - i > 0:
            n = n - i
            i += 1
        return i if n == i else i - 1
```