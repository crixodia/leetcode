# First Unique Character in a String

Difficulty: Easy
Language: Python
N: 387
Related to: Counting, Hash Table, Queue, String

Given a string `s`, *find the first non-repeating character in it and return its index*. If it does not exist, return `-1`.

**Example 1:**

```
Input: s = "leetcode"
Output: 0

```

**Example 2:**

```
Input: s = "loveleetcode"
Output: 2

```

**Example 3:**

```
Input: s = "aabb"
Output: -1

```

**Constraints:**

- `1 <= s.length <= 105`
- `s` consists of only lowercase English letters.

**Python Solution:**

```python
class Solution:
    def firstUniqChar(self, s: str) -> int:
        from collections import Counter
        freq = Counter(s)
        keys, values = list(freq.keys()), list(freq.values())
        index = -1
        if 1 in values:
            index = values.index(1)
        else:
            return index
        return s.index(keys[index])
```