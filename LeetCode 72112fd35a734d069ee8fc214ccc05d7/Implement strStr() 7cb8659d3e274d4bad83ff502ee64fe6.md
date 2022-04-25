# Implement strStr()

Difficulty: Easy
Language: Python
N: 28
Related to: String, String Matching, Two Pointers

Implement [strStr()](http://www.cplusplus.com/reference/cstring/strstr/).

Return the index of the first occurrence of needle in haystack, or `-1` if `needle` is not part of `haystack`.

**Clarification:**

What should we return when `needle` is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when `needle` is an empty string. This is consistent to C's [strstr()](http://www.cplusplus.com/reference/cstring/strstr/) and Java's [indexOf()](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#indexOf(java.lang.String)).

**Example 1:**

```
Input: haystack = "hello", needle = "ll"
Output: 2

```

**Example 2:**

```
Input: haystack = "aaaaa", needle = "bba"
Output: -1

```

**Example 3:**

```
Input: haystack = "", needle = ""
Output: 0

```

**Constraints:**

- `0 <= haystack.length, needle.length <= 5 * 104`
- `haystack` and `needle` consist of only lower-case English characters.

**Python Solution:**

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        n = len(haystack)
        m = len(needle)
        
        if m == 0:
            return 0
        elif n < m:
            return -1

        for i in range(n):
            flag = False
            if n - i >= m:
                k = 0
                j = m - 1
                while k <= j:
                    if haystack[i + k] != needle[k] or haystack[i + j] != needle[j]:
                        flag = False
                    else:
                        flag = True
                    k += 1
                    j -= 1
            if flag:
                return i
        return -1
```