# Reverse Vowels of a String

Difficulty: Easy
Language: Python
N: 345
Related to: String, Two Pointers

Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`, and they can appear in both cases.

**Example 1:**

```
Input: s = "hello"
Output: "holle"

```

**Example 2:**

```
Input: s = "leetcode"
Output: "leotcede"

```

**Constraints:**

- `1 <= s.length <= 3 * 105`
- `s` consist of **printable ASCII** characters.

**Python Solution:**

```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowels = [
            "a", "e", "i", "o", "u",
            "A", "E", "I", "O", "U"
        ]
        
        S = list(s)
        i, j = 0, len(S) - 1
        
        while i <= j:
            if S[i] in vowels and S[j] in vowels:
                S[i], S[j] = S[j], S[i]
                i += 1
                j -= 1
            elif S[i] not in vowels:
                i +=1
            elif S[j] not in vowels:
                j -= 1
                
        return "".join(S)
```