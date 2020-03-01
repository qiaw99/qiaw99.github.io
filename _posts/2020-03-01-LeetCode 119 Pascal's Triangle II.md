# LeetCode 119 Pascal's Triangle II
Given a non-negative index k where k ≤ 33, return the kth index row of the Pascal's triangle.

Note that the row index starts from 0.

In Pascal's triangle, each number is the sum of the two numbers directly above it.

### Example:
> Input: 3

> Output: [1,3,3,1]

## Python Solution
```python
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        res = [1, 1]
        if(rowIndex == 0):
            return [1]
        elif(rowIndex == 1):
            return res

        for i in range(2, rowIndex + 1):
            counter = 1
            temp = [1, 1]
            # shoud add len(res[i - 1]) - 1 elements in to temp
            for j in range(len(res) - 1):
                temp.insert(counter, res[j] + res[j + 1])
                counter += 1
            res = temp
        return res        
```
