2025-08-19 23:08

Status:
Tag: [[Software Engineering]] [[Algorithms]] [[Two Pointer]] [[leetcode]]

# Two Pointer Method

## What is it?
Two Pointer is technique where you use two indices (pointers)
 to scan through a list, string, or array in a way that reduces unnecessary work. Instead of brute force checking every possible combination, you use two moving pointers to systematically shrink the problem space.

## Common Pointer Configs
1. Opposite Ends (start, end)
2. Both start at beginning(fast & slow pointers)
3. sliding window style (left & right expand/contract window)

## When to use?
- Sorted input problems
- Strings/arrays when you're comparing characters/numbers from oppposite ends
- Linked Lists problems
- Window Scanning problems

## Why does it matter?
You avoid brute force O(n²)
You only scan once or twice at most

## Example