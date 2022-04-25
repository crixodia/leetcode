# Ransom Note

Difficulty: Easy
Language: Python
N: 383
Related to: Counting, Hash Table, String

Given two strings `ransomNote` and `magazine`, return `true` *if* `ransomNote` *can be constructed from* `magazine` *and* `false` *otherwise*.

Each letter in `magazine` can only be used once in `ransomNote`.

**Example 1:**

```
Input: ransomNote = "a", magazine = "b"
Output: false

```

**Example 2:**

```
Input: ransomNote = "aa", magazine = "ab"
Output: false

```

**Example 3:**

```
Input: ransomNote = "aa", magazine = "aab"
Output: true

```

**Constraints:**

- `1 <= ransomNote.length, magazine.length <= 105`
- `ransomNote` and `magazine` consist of lowercase English letters.

**Python Solution:**

```python
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        cr = Counter(ransomNote)
        cm = Counter(magazine)
        for c in cr:
            if c not in cm:
                return False
            elif cm[c] < cr[c]:
                return False
        return True
```