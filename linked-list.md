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

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/
```python 
def reverseList(self, head: ListNode) -> ListNode:
    prev = None
    current = head
    while current:
        temp = current.next
        current.next = prev
        prev = current
        current = temp
    return prev
def isEqual(self, first: ListNode, second: ListNode) -> bool:
    while second:
        if second.val != first.val:
            return False
        second = second.next
        first = first.next
    return True
def isPalindrome(self, head: ListNode) -> bool:
    if not head or not head.next:
        return True
    prev = None
    slow = head
    fast = head
    while fast.next and fast.next.next:
        prev = slow
        slow = slow.next
        fast = fast.next.next
    
    secondHalf = slow.next
    if fast.next: # even length
        slow.next = None
        firstHalf = self.reverseList(head)
    else: # odd length
        prev.next = None
        firstHalf = self.reverseList(head)
    return self.isEqual(firstHalf, secondHalf)
```

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

## Linked List Cycle
https://leetcode.com/problems/linked-list-cycle/

## Reorder List
https://leetcode.com/problems/reorder-list/

## Intersection of Two Linked Lists
https://leetcode.com/problems/intersection-of-two-linked-lists/

## Sort List
https://leetcode.com/problems/sort-list/
