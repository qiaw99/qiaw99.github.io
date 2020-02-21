# LeetCode 58 Length of Last Word
### Requirements:
Given a string s consists of upper/lower-case alphabets and empty space characters ' ', return the length of last word (last word means the last appearing word if we loop from left to right) in the string.

If the last word does not exist, return 0.

### Note: 
A word is defined as a maximal substring consisting of non-space characters only.

### Example:
> Input: "Hello World"

> Output: 5

__*Time complexity in the worst case is O(n)*__
## Python Solution
`````python
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        if(s == " "):
            return 0
        res = s.split(" ")
        for i in range(len(res) - 1, -1, -1):
            if(res[i] != ''):
                return len(res[i])
        return 0
`````
