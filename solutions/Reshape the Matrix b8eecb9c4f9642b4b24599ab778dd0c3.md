# Reshape the Matrix

Difficulty: Easy
Language: Python
N: 566
Related to: Array, Matrix, Simulation

In MATLAB, there is a handy function called `reshape` which can reshape an `m x n` matrix into a new one with a different size `r x c` keeping its original data.

You are given an `m x n` matrix `mat` and two integers `r` and `c` representing the number of rows and the number of columns of the wanted reshaped matrix.

The reshaped matrix should be filled with all the elements of the original matrix in the same row-traversing order as they were.

If the `reshape` operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

**Example 1:**

![https://assets.leetcode.com/uploads/2021/04/24/reshape1-grid.jpg](https://assets.leetcode.com/uploads/2021/04/24/reshape1-grid.jpg)

```
Input: mat = [[1,2],[3,4]], r = 1, c = 4
Output: [[1,2,3,4]]

```

**Example 2:**

![https://assets.leetcode.com/uploads/2021/04/24/reshape2-grid.jpg](https://assets.leetcode.com/uploads/2021/04/24/reshape2-grid.jpg)

```
Input: mat = [[1,2],[3,4]], r = 2, c = 4
Output: [[1,2],[3,4]]

```

**Constraints:**

- `m == mat.length`
- `n == mat[i].length`
- `1 <= m, n <= 100`
- `1000 <= mat[i][j] <= 1000`
- `1 <= r, c <= 300`

**Python Solution:**

```python
class Solution:
    def matrixReshape(self, mat: List[List[int]], r: int, c: int) -> List[List[int]]:
        m = len(mat)
        n = len(mat[0])
        if m*n != r*c:
            return mat
        
        _i, _j, k = 0, 0, 0
        new = [[0]*c for i in range(r)]
        for i in range(m):
            for j in range(n):
                new[_i][_j] = mat[i][j]
                k += 1
                _j += 1
                if k == c:
                    k, _j = 0, 0
                    _i += 1
        return new
```