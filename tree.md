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
```python
def levelOrder(self, root: TreeNode) -> List[List[int]]:
    result = []
    if root is None:
        return result
    queue = [root]
    while queue:
        level = []
        qsize = len(queue)
        for _ in range(qsize):
            node = queue.pop(0)
            if node is not None:
                level.append(node.val)
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
        result.append(level)
    return result
```



## Subtree Of Another Tree

https://leetcode.com/problems/subtree-of-another-tree/


## Kth Smallest Element In a BST

https://leetcode.com/problems/kth-smallest-element-in-a-bst/


## Validate Binary Search Tree

https://leetcode.com/problems/validate-binary-search-tree/


## Binary Search Tree Iterator

https://leetcode.com/problems/binary-search-tree-iterator/


