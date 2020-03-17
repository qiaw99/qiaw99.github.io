# LeetCode 155 Min Stack
Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

- push(x) -- Push element x onto stack.
- pop() -- Removes the element on top of the stack.
- top() -- Get the top element.
- getMin() -- Retrieve the minimum element in the stack.
 

### Example:

    MinStack minStack = new MinStack();
    minStack.push(-2);
    minStack.push(0);
    minStack.push(-3);
    minStack.getMin();   --> Returns -3.
    minStack.pop();
    minStack.top();      --> Returns 0.
    minStack.getMin();   --> Returns -2.

## Python Solution
```python
class MinStack:

    def __init__(self):
        """
        initialize your data structure here.
        """
        self.ls = []
        
    def push(self, x: int) -> None:
        self.ls.append(x)

    def pop(self) -> None:
        self.ls.pop(-1)

    def top(self) -> int:
        return self.ls[-1]

    def getMin(self) -> int:
        return min(self.ls)


# Your MinStack object will be instantiated and called as such:
# obj = MinStack()
# obj.push(x)
# obj.pop()
# param_3 = obj.top()
```

## Java solution
With other data structure, the efficiecy might be better than ArrayList...
```java
class MinStack {
    ArrayList<Integer> ls;
    /** initialize your data structure here. */
    public MinStack() {
        ls = new ArrayList<Integer>();
    }
    
    public void push(int x) {
        this.ls.add(x);
    }
    
    public void pop() {
        this.ls.remove(ls.size() - 1);
    }
    
    public int top() {
        return this.ls.get(ls.size() - 1);
    }
    
    public int getMin() {
        return Collections.min(ls);
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
```
