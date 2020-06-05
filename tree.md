# Tree

+ [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)
+ [Symmetric Tree](#symmetric-tree)
+ [Maximum Depth Of Binary Tree](#maximum-depth-of-binary-tree)
+ [Same Tree](#same-tree)
+ [Invert Binary Tree](#invert-binary-tree)
+ [Path Sum](#path-sum)
+ [Binary Tree Level Order Traversal](#binary-tree-level-order-traversal)
+ [Subtree Of Another Tree](#subtree-of-another-tree)
+ [Kth Smallest Element In a BST](#kth-smallest-element-in-a-bst)
+ [Validate Binary Search Tree](#validate-binary-search-tree)
+ [Binary Search Tree Iterator](#binary-search-tree-iterator)


## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/



## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/



## Maximum Depth Of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree/



## Same Tree

https://leetcode.com/problems/same-tree/



## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/



## Path Sum

https://leetcode.com/problems/path-sum/



## Binary Tree Level Order Traversal

https://leetcode.com/problems/binary-tree-level-order-traversal/



## Subtree Of Another Tree

https://leetcode.com/problems/subtree-of-another-tree/


## Kth Smallest Element In a BST

https://leetcode.com/problems/kth-smallest-element-in-a-bst/


## Validate Binary Search Tree

https://leetcode.com/problems/validate-binary-search-tree/


## Binary Search Tree Iterator

https://leetcode.com/problems/binary-search-tree-iterator/
```python
class BSTIterator:
    def __init__(self, root: TreeNode):
        self.stack = list()
        self.addLeft(root)

    def addLeft(self, root):
        while root:
            self.stack.append(root)
            root = root.left

    def next(self) -> int:
        top = self.stack.pop()
        if top.right:
            self.addLeft(top.right)
        return top.val

    def hasNext(self) -> bool:
        return len(self.stack) > 0
        
````


