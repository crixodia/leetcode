# Transpose Matrix

Difficulty: Easy
Language: Python
N: 867
Related to: Array, Math, Simulation

Given a 2D integer array `matrix`, return *the **transpose** of* `matrix`.

The **transpose** of a matrix is the matrix flipped over its main diagonal, switching the matrix's row and column indices.

![https://assets.leetcode.com/uploads/2021/02/10/hint_transpose.png](https://assets.leetcode.com/uploads/2021/02/10/hint_transpose.png)

**Example 1:**

```
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[1,4,7],[2,5,8],[3,6,9]]

```

**Example 2:**

```
Input: matrix = [[1,2,3],[4,5,6]]
Output: [[1,4],[2,5],[3,6]]

```

**Constraints:**

- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 1000`
- `1 <= m * n <= 105`
- `109 <= matrix[i][j] <= 109`

**Python Solution:**

```python
class Solution:
    def transpose(self, matrix: List[List[int]]) -> List[List[int]]:
        row, col = len(matrix), len(matrix[0])
        t = [[0]*row for i in range(col)]
        for i in range(col):
            for j in range(row):
                t[i][j] = matrix[j][i]
        return t
```