# LeetCode 14 Longest Common Prefix

## Requirements:
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

### Example 1:
> Input: ["flower","flow","flight"]

> Output: "fl"

### Example 2:
> Input: ["dog","racecar","car"]

> Output: ""

> Explanation: There is no common prefix among the input strings.

### Note:
All given inputs are in lowercase letters a-z.

## Python Solution
```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if strs == []:
            return ''
        counter = 0
        length = min(len(string) for string in strs)
        for i in range(length):
            temp = strs[0][i]
            for j in range(len(strs)):
                if(strs[j][i] != temp):
                    if counter == 0:
                        return ""
                    return strs[0][:counter]
            counter += 1
        return strs[0][:counter]        
        
```
__Time complexity = O(n2)__ 
