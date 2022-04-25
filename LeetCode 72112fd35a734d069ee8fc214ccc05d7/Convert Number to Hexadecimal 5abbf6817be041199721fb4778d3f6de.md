# Convert Number to Hexadecimal

Difficulty: Easy
Language: Python
N: 405
Related to: Bit Manipulation, Math

Given an integer `num`, return *a string representing its hexadecimal representation*. For negative integers, [two’s complement](https://en.wikipedia.org/wiki/Two%27s_complement) method is used.

All the letters in the answer string should be lowercase characters, and there should not be any leading zeros in the answer except for the zero itself.

**Note:** You are not allowed to use any built-in library method to directly solve this problem.

**Example 1:**

```
Input: num = 26
Output: "1a"

```

**Example 2:**

```
Input: num = -1
Output: "ffffffff"

```

**Constraints:**

- `231 <= num <= 231 - 1`

**Python Solution:**

```python
class Solution:
    def toHex(self, num: int) -> str:
        if num < 0:
            s = list(range(8))
            s = list(map(lambda x: 16**x, s))
            s = 15*sum(s) + 1
            num = s + num
        elif num == 0:
            return "0"
        
        values = {10:'a', 11:'b', 12:'c', 13:'d', 14:'e', 15:'f'}
        hx = ""
        n = num
        while n > 0:
            n, c = divmod(n, 16)            
            hx = (str(c) if c < 10 else values[c]) + hx
        return hx
```