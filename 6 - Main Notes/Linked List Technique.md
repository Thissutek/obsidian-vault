2025-08-20 16:16

Status:
Tag: [[Software Engineering]] [[Data Structures]] [[Linked List]] [[leetcode]]

# Linked List Technique

## What is it?
A linked list is a linear collection of nodes where each node contains 
1. Data -> the value it stores
2. Pointer (next) -> a reference to the next node in the list

Unlike arrays Elements are not stored in contiguous memory, you can't access the element by index in O(1). You have to traverse from the head. 

Types of linked lists
- Singly Linked List -> each node points to the next
- Doubly Linked List -> each node points to both next and previous nodes
- Circular Linked List -> last node points back to the head

## Why does it matter?
- Linked lists are dynamic in size -> easy to insert/delete without shifting elements like arrays
- Useful for frequent insertions/deletions in the middle of a list
- They're a building block for advanced structure (stacks, queues, graphs, LRU caches)

### Typical Use Cases
- Stacks & Queues 
- Undo/Redo Functionality
- LRU cache -> combined with a hash map for O(1) access and update
- Merging sorted lists -> classic interview problems
- Dynamic memory allocation 

## Example