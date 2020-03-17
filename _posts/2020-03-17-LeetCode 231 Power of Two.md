# LeetCode 231 Power of Two
Given an integer, write a function to determine if it is a power of two.

### Example 1:
> Input: 1

> Output: true 

> Explanation: 20 = 1

### Example 2:
> Input: 16

> Output: true

> Explanation: 24 = 16

### Example 3:
> Input: 218

> Output: false

## C Solution with recursion
`````c
bool isPowerOfTwo(int n){
    if(n <= 0){
        return false;
    }else if(n == 1){
        return true;
    }else{
        if(n % 2 == 1)
            return false;
        return isPowerOfTwo(n / 2);
    }
}
`````

## Python solution with logarithmic
```python
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        if(n <= 0):
            return False
        temp = math.log2(n)
        return temp == int(temp)
```
