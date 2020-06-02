# linked-list
+[Reverse Linked List](#reverse-linked-list)
+[Middle of the Linked List](#middle-of-the-linked-list)
+[Palindrome Linked List](#palindrome-linked-list)
+[Merge Two Sorted Lists](#merge-two-sorted-lists)
+[Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
+[Linked List Cycle II](#linked-list-cycle-ii)
+[Linked List Cycle](#linked-list-cycle)
+[Reorder List](#reorder-list)
+[Intersection of Two Linked Lists](#intersection-of-two-linked-lists)
+[Sort List](#sort-list)


## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

##Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

##Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

##Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/
```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    L_Final = ListNode()
    cur = L_Final
    while l1 and l2:
        if l1.val < l2.val:
            cur.next = ListNode(l1.val)
            l1 = l1.next
        else:
            cur.next = ListNode(l2.val)
            l2 = l2.next
        cur = cur.next
    if l1:
        cur.next = l1
    if l2:
        cur.next = l2
    return L_Final.next

```
##Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

##Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

##Linked List Cycle
https://leetcode.com/problems/linked-list-cycle/

##Reorder List
https://leetcode.com/problems/reorder-list/

##Intersection of Two Linked Lists
https://leetcode.com/problems/intersection-of-two-linked-lists/

##Sort List
https://leetcode.com/problems/sort-list/
