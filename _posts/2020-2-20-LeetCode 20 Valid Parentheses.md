# LeetCode 20 Valid Parentheses
## Requirements:
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

__An input string is valid if:__

- Open brackets must be closed by the same type of brackets.
- Open brackets must be closed in the correct order.
- Note that an empty string is also considered valid.

---
### Example 1:
> Input: "( )"

> Output: true

### Example 2:
> Input: "( )[ ]{ }"

> Output: true

### Example 3:
> Input: "( ]"

> Output: false

### Example 4:
> Input: "( [ ) ]"

> Output: false

### Example 5:
> Input: "{ [ ] }"

> Output: true
## Python Solution
```python
class Solution:
    def isValid(self, s: str) -> bool:
        if(len(s) == 0):
            return True
        if(len(s) % 2 != 0):
            return False
            
        pairs = {')': '(', ']': '[', '}': '{' }
        opening = {'(', '[', '{'}
        stack = []
        
        for c in s:
            if(c in opening):
                stack.append(c)
            if(c in pairs):
                if(len(stack) >= 1 and pairs[c] == stack[-1]):
                    stack.pop()
                else:
                    return False
        return len(stack) == 0
```
__Time complexity = O(n)__ 
