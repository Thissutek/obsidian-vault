2026-04-11 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Data Structures]]

# Binary Search Trees

## What is it?
A Binary Search Tree (BST) is a data structure that stores values in a sorted manner, allowing for efficient searching, insertion, and deletion. In a BST, each node has at most two children, and for any given node, all values in the left subtree are less than the node's value, while all values in the right subtree are greater.

## Why does it matter?
Binary Search Trees are important because they provide a way to maintain a dynamically ordered collection of items, enabling quick search operations. In large datasets, the average time complexity for search, insertion, and deletion operations in a balanced BST is O(log n), making it much faster than linear searches, especially as data size grows.

## Example
Here's a simple implementation of a Binary Search Tree in Python:

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

class BST:
    def insert(self, root, value):
        if not root:
            return Node(value)
        elif value < root.value:
            root.left = self.insert(root.left, value)
        else:
            root.right = self.insert(root.right, value)
        return root

# Example usage
bst = BST()
root = None
values = [10, 5, 15, 3, 7]
for v in values:
    root = bst.insert(root, v)
```

In this example, we define a `Node` class for the tree nodes and a `BST` class with an `insert` method to place elements into the tree while maintaining its sorted properties.