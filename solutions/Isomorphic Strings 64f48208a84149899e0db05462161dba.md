# Isomorphic Strings

Difficulty: Easy
Language: Python
N: 205
Related to: Hash Table, String

Given two strings `s` and `t`, *determine if they are isomorphic*.

Two strings `s` and `t` are isomorphic if the characters in `s` can be replaced to get `t`.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

**Example 1:**

```
Input: s = "egg", t = "add"
Output: true

```

**Example 2:**

```
Input: s = "foo", t = "bar"
Output: false

```

**Example 3:**

```
Input: s = "paper", t = "title"
Output: true

```

**Constraints:**

- `1 <= s.length <= 5 * 104`
- `t.length == s.length`
- `s` and `t` consist of any valid ascii character.

**Python Solution:**

```python
class Solution:
    def isomorphic(self, s:str, t:str) -> bool:
        D = {}
        
        for i, c in enumerate(s):
            if c not in D:
                D[c] = t[i]
            elif D[c] != t[i]:
                return False
        
        return True
    
    def isIsomorphic(self, s: str, t: str) -> bool:
        return self.isomorphic(s,t) and self.isomorphic(t,s)
```