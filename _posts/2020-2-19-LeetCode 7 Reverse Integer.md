# LeetCode 7 Reverse Integer
## Requirements:
Given a 32-bit signed integer, reverse digits of an integer.

#### Example 1:
> Input: 123

> Output: 321

#### Example 2:
> Input: -123

> Output: -321

#### Example 3:
> Input: 120
> Output: 21

### Note:
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

## Python Solution
```python
class Solution:
    def reverse(self, x: int) -> int:
        counter = 1
        res = []
        temp = -1
        summe = 0
        length = len(str(x))
        string = str(x)
        
        if x < 0:
            length -= 1
            temp = 0
            
        for i in range(len(str(x)) - 1, temp, -1):
            summe += int(string[i]) * (10 ** (length - counter))
            counter += 1

        if(temp == 0):
            if (-1) * summe >= -(2 ** 31):
                return -1 * summe
            return 0
        else:
            if summe < 2 ** 31 - 1:
                return summe
            return 0            
        
```
__Time complexity = O(n)__ 
