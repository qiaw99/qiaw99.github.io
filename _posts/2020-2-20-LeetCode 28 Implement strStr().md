# LeetCode 28 Implement strStr()
### Requirements:
Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

### Example 1:
> Input: haystack = "hello", needle = "ll"

> Output: 2

### Example 2:
> Input: haystack = "aaaaa", needle = "bba"

> Output: -1

### Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

### Extra info:
__Time complexity = O((m - n - 1) * n)__ 

I have just used the most naive method for string matching. Of course, KMP, Boyer & Moore or Rabin-Karp algorithms can be used. --> O(m + n)

## Python Solution
`````python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        m = len(haystack)
        n = len(needle)
        if(n == 0):
            return 0
        if(n > m):
            return -1
        for i in range(m - n + 1):
            if(haystack[i : i + n] == needle):
                return i
        return -1
`````
