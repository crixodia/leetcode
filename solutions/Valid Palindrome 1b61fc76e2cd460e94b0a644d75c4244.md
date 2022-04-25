# Valid Palindrome

Difficulty: Easy
Language: Python
N: 125
Related to: String, Two Pointers

A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` *if it is a **palindrome**, or* `false` *otherwise*.

**Example 1:**

```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

```

**Example 2:**

```
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

```

**Example 3:**

```
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

```

**Constraints:**

- `1 <= s.length <= 2 * 105`
- `s` consists only of printable ASCII characters.

**Python Solution:**

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        S = list(map(lambda c: c.upper() if str.isalnum(c) else '', s))
        S = ''.join(S)
        S = S.replace(" ","")
        return S == S[::-1]
```