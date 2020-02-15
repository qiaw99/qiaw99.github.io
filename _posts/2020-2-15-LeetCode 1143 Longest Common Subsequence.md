# LeetCode 1143 Longest Common Subsequence

## Requirement
Given two strings text1 and text2, return the length of their longest common subsequence.

A subsequence of a string is a new string generated from the original string with some characters(can be none) deleted without changing the relative order of the remaining characters. (eg, "ace" is a subsequence of "abcde" while "aec" is not). A common subsequence of two strings is a subsequence that is common to both strings.

If there is no common subsequence, return 0.

 

#### Example 1:
> Input: text1 = "abcde", text2 = "ace" 

> Output: 3  

> __Explanation: The longest common subsequence is "ace" and its length is 3.__

#### Example 2:
> Input: text1 = "abc", text2 = "abc"
> Output: 3
> __Explanation: The longest common subsequence is "abc" and its length is 3.__

#### Example 3:
> Input: text1 = "abc", text2 = "def"

> Output: 0

> __Explanation: There is no such common subsequence, so the result is 0.__
 
## Constraints:
1 <= text1.length <= 1000 

1 <= text2.length <= 1000

The input strings consist of lowercase English characters only.

## Code
```python
# 35678
s = [1,3,4,5,6,7,7,8]
t = [3,5,7,4,8,6,7,8,2]
dp = [[0 for _ in range(len(t))] for _ in range(len(s))]
for i in range(0, len(s)):
    for j in range(0, len(t)):
        if s[i] == t[j]:
            dp[i][j] = dp[i - 1][j - 1] + 1
        else:
            dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])
print(dp[len(s) - 1][len(t) - 1])
```




