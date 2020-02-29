# LeetCode 107 Binary Tree Level Order Traversal II
Given a binary tree, return the bottom-up level order traversal of its nodes' values. (ie, from left to right, level by level from leaf to root).

### For example:
Given binary tree [3,9,20,null,null,15,7],

```
    3
   / \
  9  20
    /  \
   15   7
```

return its bottom-up level order traversal as:
```
[
  [15,7],
  [9,20],
  [3]
]
```


## Python Solution using BFS
`````python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def levelOrderBottom(self, root: TreeNode) -> List[List[int]]:
        # bfs
        level = {root: 0}
        i = 1
        frontier = {root}
        while frontier:
            next = []
            for u in frontier:
                temp = []
                if(u == None):
                    pass
                else:
                    if(u.left != None):
                        temp.append(u.left)
                    if(u.right != None):
                        temp.append(u.right)
                for v in temp:
                    if v not in level:
                        level[v] = i
                        next.append(v)
            frontier = next
            i += 1
            
        res = []
        maximum = max(level.values())
        for i in range(maximum, -1, -1):
            temp = []
            for k in level.keys():
                if(level[k] == i):
                    if(k != None):
                        temp.append(k.val)
            if(temp != []):
                res.append(temp)
        return res
            
`````

## Java solution using DFS:
```java
class Solution {
    public List<List<Integer>> levelOrderBottom(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        dfs(root,0,res);
        Collections.reverse(res);
        return res;
    }
    public void dfs(TreeNode root, int level, List<List<Integer>> res){
        if(root == null) return;
        if(res.size() == level) res.add(new ArrayList<Integer>());
        dfs(root.left, level+1, res);
        res.get(level).add(root.val);
        dfs(root.right, level+1, res);
    }
}
```
