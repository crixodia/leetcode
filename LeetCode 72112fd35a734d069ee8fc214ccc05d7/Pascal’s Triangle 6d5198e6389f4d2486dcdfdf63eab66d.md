# Pascal’s Triangle

Difficulty: Easy
Language: Python
N: 118
Related to: Array, Dynamic Programming

Given an integer `numRows`, return the first numRows of **Pascal's triangle**.

In **Pascal's triangle**, each number is the sum of the two numbers directly above it as shown:

![https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

**Example 1:**

```
Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]

```

**Example 2:**

```
Input: numRows = 1
Output: [[1]]

```

**Constraints:**

- `1 <= numRows <= 30`

**Python Solution:**

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        def factorial(n):
            if n <= 1:
                return 1
            else:
                return n*factorial(n-1)
        
        def nck(n, k):
            return factorial(n)/(factorial(k)*factorial(n-k))
        
        pascal = []
        for n in range(numRows):
            row = [1]*(n+1)
            for k in range(n):
                row[k] = int(nck(n, k))
            pascal.append(row)
            
        return pascal
```