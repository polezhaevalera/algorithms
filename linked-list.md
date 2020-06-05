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

## Merge Two Sorted Lists
https://leetcode.com/problems/merge-two-sorted-lists/

```python
#решение через рекурсию 
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    if not l1:
        return l2
    if not l2:
        return l1
    if l1.val < l2.val:
        l1.next = self.mergeTwoLists(l1.next, l2)
        return l1
    else:
        l2.next = self.mergeTwoLists(l1, l2.next)
        return l2
```



## Remove Nth Node From End of List
https://leetcode.com/problems/remove-nth-node-from-end-of-list/
```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    fast = slow = head

    for _ in range(n):
        fast = fast.next

    if not fast:
        return head.next

    while fast.next:
        fast = fast.next
        slow = slow.next
    slow.next = slow.next.next
    return head
```

## Linked List Cycle II
https://leetcode.com/problems/linked-list-cycle-ii/
```python
def detectCycle(self, head: ListNode) -> ListNode:
    temp = head
    a = []
    while temp:
        if temp not in a:
            a.append(temp)
        else:
            return temp
        temp = temp.next
    return None
```

## Linked List Cycle
https://leetcode.com/problems/linked-list-cycle/
```python
def hasCycle(self, head: ListNode) -> bool:
    l = {}
    while head:
        if(head in l):
            return True
        else:
            l[head] = True
        head = head.next
    return False
```

## Reorder List
https://leetcode.com/problems/reorder-list/
```python 
def reorderList(self, head: ListNode) -> None:
    if not head or not head.next:
        return head
    stack = []
    slo = head
    fst = head
    prev = slo
    while fst and fst.next:
        prev = slo
        slo = slo.next
        fst = fst.next.next
    prev.next = None
    while slo:
        stack.append(slo)
        slo = slo.next
    temp = head
    temp2 = head.next
    while temp2:
        temp.next = stack.pop()
        temp.next.next = temp2
        temp = temp2
        temp2 = temp2.next
    while stack:
        temp.next = stack.pop()
        temp = temp.next
    temp.next = None

```
## Intersection of Two Linked Lists
https://leetcode.com/problems/intersection-of-two-linked-lists/
```python
def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
    temp1 = headA
    temp2 = headB
    d = {}
    while temp1:
        d[temp1] = temp1
        temp1 = temp1.next
    while temp2:
        if temp2 in d:
            return temp2
        temp2 = temp2.next
    return None

```
## Sort List
https://leetcode.com/problems/sort-list/
```python
def merge(self, left: ListNode, right: ListNode) -> ListNode:
    head = ListNode(0)
    current = head
    while left and right:
        if left.val <= right.val:
            current.next = left
            left = left.next
        else:
            current.next = right
            right = right.next
        current = current.next
    if not left:
        current.next = right
    elif not right:
        current.next = left
    return head.next


def sortList(self, head: ListNode) -> ListNode:
    if not head or not head.next:
        return head
    mid = head
    temp = head
    while mid.next and temp.next and temp.next.next:
        mid = mid.next
        temp = temp.next.next
    right = self.sortList(mid.next)
    mid.next = None
    left = self.sortList(head)
    return self.merge(left, right)

```
