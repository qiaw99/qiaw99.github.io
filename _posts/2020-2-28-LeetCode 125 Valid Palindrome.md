# LeetCode 125 Valid Palindrome
Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

### Note: For the purpose of this problem, we define empty string as valid palindrome.

### Example 1:
> Input: "A man, a plan, a canal: Panama"

> Output: true

### Example 2:
> Input: "race a car"

> Output: false

## Python Solution
- The naive way to solve:
`````python
class Solution:
    def isPalindrome(self, s: str) -> bool:

        res = []
        for i in range(len(s)):
            if(s[i].isalnum()):
                res.append(s[i].lower())
        return res == res[::-1]
`````
> Although the time complexity is O(n), this algorithm is still not quite efficient. Meanwhile, this algo needs O(n) space.

- With two pointers
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        i = 0
        j = len(s) - 1
        while(i <= j):
            if(not s[i].isalnum()):
                i += 1
                continue
            if(not s[j].isalnum()):
                j -= 1
                continue
            if(s[i].lower() == s[j].lower()):
                i += 1
                j -= 1
            else:
                return False
```
