# Excel Sheet Column Title

Difficulty: Easy
Language: Python
N: 168
Related to: Math, String

Given an integer `columnNumber`, return *its corresponding column title as it appears in an Excel sheet*.

For example:

```
A -> 1
B -> 2
C -> 3
...
Z -> 26
AA -> 27
AB -> 28
...

```

**Example 1:**

```
Input: columnNumber = 1
Output: "A"

```

**Example 2:**

```
Input: columnNumber = 28
Output: "AB"

```

**Example 3:**

```
Input: columnNumber = 701
Output: "ZY"
```

**Python Solution:**

```python
class Solution:
    def convertToTitle(self, columnNumber: int) -> str:
        a = columnNumber
        b = 0
        col = ""
        while a > 26:
            a, b = divmod(a, 26)
            if b == 0:
                b = 26
                a = a - 1
            col = chr(64 + b) + col
        col = chr(64 + a) + col
        return col
```