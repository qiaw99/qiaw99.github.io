# LeetCode 67 Add Binary
### Requirements:
Given two binary strings, return their sum (also a binary string).

The input strings are both non-empty and contains only characters 1 or 0.

### Example 1:
> Input: a = "11", b = "1"

> Output: "100"

### Example 2:
> Input: a = "1010", b = "1011"

> Output: "10101"

__*Time complexity in the worst case is O(n)*__
## Python Solution
`````python
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        m = len(a)
        n = len(b)
        res = ''
        if(m > n):
            temp = m
            b = '0' * (m - n) + b
        else:
            temp = n
            a = '0' * (n - m) + a
        flag = 0
        
        for i in range(temp - 1, -1, -1):
            if(int(a[i]) + int(b[i]) + flag < 2):
                res += str(int(a[i]) + int(b[i]) + flag)
                flag = 0
            else:
                res += str(int(a[i]) + int(b[i]) + flag - 2)
                if(i == 0):
                    res += '1'
                flag = 1
        return res[::-1]
`````
