2025-08-20 16:17

Status:
Tag: [[Software Engineering]] [[Data Structures]] [[Linked List]] [[Linked List Technique]] [[leetcode]]
# Reverse Linked List
## Problem
Given the beginning of a singly linked list `head`, reverse the list, and return the new beginning of the list.

**Example 1:**

```java
Input: head = [0,1,2,3]

Output: [3,2,1,0]
```

**Example 2:**

```java
Input: head = []

Output: []
```

## Constraints

- `0 <= The length of the list <= 1000`.
- `-1000 <= Node.val <= 1000`
## My Thoughts
Well first we would have to make the end of the list the new head and make each one before it point to the reference before it. 

## Plan Pseudocode

```
function reverseLinkedList(head):
	prev = null
	current = head
	
	while current is not null:
		nextTemp = current.next
		current.next = prev
		prev = current
		current = nextTemp
		
	return prev
```
## Solution
```
class Solution {
    /**
     * @param {ListNode} head
     * @return {ListNode}
     */
    reverseLinkedList(head) {
        let prev = null;
        let current = head;

        while (current !== null) {
            let nextTemp = current.next; // save next node
            current.next = prev;         // reverse the link
            prev = current;              // move prev forward
            current = nextTemp;          // move current forward
        }

        return prev; // prev is new head
    }
}

```

## Notes
Review this one again I remember this problem. Its basically kind of like everytime we are going through the nodes normally we are just kind of erasing where the pointer is cause we need to set the pointer to be the opposite way which is why the prev is the current.next its a little confusing I might need to draw this out.