# Fibonacci Number

Difficulty: Easy
Language: Python
N: 509
Related to: Dynamic Programming, Math, Memoization, Recursion

The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```
F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.

```

Given `n`, calculate `F(n)`.

**Example 1:**

```
Input: n = 2
Output: 1
Explanation: F(2) = F(1) + F(0) = 1 + 0 = 1.

```

**Example 2:**

```
Input: n = 3
Output: 2
Explanation: F(3) = F(2) + F(1) = 1 + 1 = 2.

```

**Example 3:**

```
Input: n = 4
Output: 3
Explanation: F(4) = F(3) + F(2) = 2 + 1 = 3.

```

**Constraints:**

- `0 <= n <= 30`

**Python Solution:**

```python
class Solution:
    def Fib(self, n, memo):
        if not n in memo:
            memo[n] = self.Fib(n-1, memo) + self.Fib(n-2, memo)
        return memo[n]
    
    def fib(self, n: int) -> int:
        return self.Fib(n, [0,1]+[-1]*(n-1))
```

```python
class Solution:
    def climbStairs(self, n: int) -> int:
        def fib_memo(n, m):
            try:
                return m[n]
            except:
                r = fib_memo(n-2, m) + fib_memo(n-1, m)
                m.append(r)
                return r
            
        return fib_memo(n, [1,1])
```