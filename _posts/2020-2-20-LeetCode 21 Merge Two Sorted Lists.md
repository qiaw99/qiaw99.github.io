# LeetCode 21 Merge Two Sorted Lists
## Requirements:
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

---
### Example:
> Input: 1->2->4, 1->3->4

> Output: 1->1->2->3->4->4

---
## Python Solution
__The definition of class ListNode:__
```python
class ListNode:
	def __init__(self, x):
		self.val = x
		self.next = None
```

- Recursive: 
```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        if not l1:
            return l2
        if not l2:
            return l1
        if(l1.val <= l2.val):
            l1.next = self.mergeTwoLists(l1.next, l2)
            return l1
        else:
            l2.next = self.mergeTwoLists(l1, l2.next)
            return l2
```

- Iterative:
```python
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        list1 = l1
        list2 = l2
		
		# Create a new list. The head pointer will traverse the new list while
		# the current pointer will point to the head of the new list. Since the current pointer won't be moving,
		# It'll be our return value. We'll also be returning current.next since -1 is just a filler.
		
        head = current = ListNode(-1)
		
		# The loop below will traverse list1 and list2. If the value in list1 is <= the value in list2, we add that value 
		# to the new list and advance list1 to point to the next node. Similarly if the value in list2 is smaller than the value in list1
		# we add that value to the new list and advance list2 to point to the next node. Note that only the pointer with 
		# the smaller value is advanced to point to the next node
        
        while list1 is not None and list2 is not None:
            if list1.val <= list2.val:
                head.next = ListNode(list1.val)
                head = head.next
                list1 = list1.next
            else:
                head.next = ListNode(list2.val)
                head = head.next
                list2 = list2.next
        
		# For the code below, if we exhaust the values in list1 then we have to add all the remaining values from list2 to the new list. 
		# Similarly, if we exhaust all the values in list2 then we have to add the remaining values in list1 to the new list.
		
        if list1 is None and list2 is None:
            return current.next
        elif list1 is None:
            while list2 is not None:
                head.next = ListNode(list2.val)
                head = head.next
                list2 = list2.next
        else:
            while list1 is not None:
                head.next = ListNode(list1.val)
                head = head.next
                list1 = list1.next
        
        return current.next
```
__Time complexity = O(n)__ 
