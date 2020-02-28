# LeetCode 83 Remove Duplicates from Sorted List
Given a sorted linked list, delete all duplicates such that each element appear only once.

### Example 1:
> Input: 1->1->2

> Output: 1->2

### Example 2:
> Input: 1->1->2->3->3

> Output: 1->2->3

__*Time complexity in the worst case is O(n)*__

## Python Solution
`````python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        if(head == None):
            return None
        if(head.next == None):
            return head
        cur = head.next
        prev = head
        res = head
        
        while(cur != None):
            if(cur.val == prev.val):
                cur = cur.next
            else:
                prev.next = cur
                prev = cur
                cur = cur.next
                
        if(prev.next != None):
            prev.next = None
        return res
                
`````
