# LeetCode 100 Same Tree
Given two binary trees, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical and the nodes have the same value.

### Example 1:

__Input:__    
```
   1         1

  / \       / \

 2   3     2   3
```
> [1,2,3],   [1,2,3]

__Output:__ true

### Example 2:

Input:    
```
           1         1
          /           \
         2             2
```
> [1,2],     [1,null,2]

__Output:__ false

### Example 3:
__Input:__
```
           1         1
          / \       / \
         2   1     1   2
```
> [1,2,1],   [1,1,2]

__Output:__ false

__*Time complexity in the worst case is O(# number of nodes)*__

## Python Solution
`````python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def inOrder(self, p):
        if(p == None):
            return [float("inf")]
        else:
            return [p.val] + self.inOrder(p.left) + self.inOrder(p.right)
        
    def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
        return self.inOrder(p) == self.inOrder(q)

`````
