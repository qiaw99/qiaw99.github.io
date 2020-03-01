# LeetCode 118 Pascal's Triangle
Given a non-negative integer numRows, generate the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it.

### Example:
> Input: 5

> Output:
```
[
     [1],
    [1,1],
   [1,2,1],
  [1,3,3,1],
 [1,4,6,4,1]
]
```

## Python Solution
`````python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        res = [[1], [1, 1]]
        if(numRows == 0):
            return []
        elif(numRows == 1):
            return [res[0]]

        # from the 3. row on 
        for i in range(2, numRows):
            counter = 1
            temp = [1, 1]
            # shoud add len(res[i - 1]) - 1 elements in to temp
            for j in range(len(res[i - 1]) - 1):
                temp.insert(counter, res[i - 1][j] + res[i - 1][j + 1])
                counter += 1
            res.append(temp)
        return res               
`````
My solution on Leetcode: [click here](https://leetcode.com/problems/pascals-triangle/discuss/525574/Faster-than-99.49-python-3)

__Runtime: 16 ms, faster than 99.46% of Python3 online submissions for Pascal's Triangle.__

__Memory Usage: 12.7 MB, less than 100.00% of Python3 online submissions for Pascal's Triangle.__
