# LeetCode 206 Reverse Linked List 

## Requirement
Reverse a singly linked list.

Example:

> Input: 1->2->3->4->5->NULL

> Output: 5->4->3->2->1->NULL

### Follow up:

A linked list can be reversed either iteratively or recursively. Could you implement both?


## Code
### Iterative
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;
        ListNode nextTemp = null;
        while (curr != null) {
            nextTemp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = nextTemp;
        }
        return prev;
    }
}
```

### Recursive
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        if (head.next == null) 
            return head;
        ListNode last = reverseList(head.next);
        head.next.next = head;
        head.next = null;
        return last;
    }
}
```



