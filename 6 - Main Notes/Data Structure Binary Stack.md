2025-07-30 16:33

Status:
Tag: [[Software Engineering]] [[Algorithms]] [[Data Structures]] [[Binary Search]]

# Data Structure Binary Stack

## What is it?
Binary search is an efficient algorithm for finding a target value within a sorted array.
- Instead of checking each element one-by-one (which is what linear search does)
- Binary search cuts the search space in half every step, taking only O(log n) time.

## Why does it matter?
- Efficiency: its drastically faster than linear search for large datasets
- Foundational Tool: Many advanced problems reduce down to binary search in disguise
- Interview favourite: Testing understanding of binary serach helps interviewers assess algorithmic thinking

## How it works?
Think of a sorted array and a target number
1. Compares the middle element of the array to the target
2. if the middle is the target return it
3. if the target is smaller we repeat the search on the left half
4. if the target is larger we repeat the search on the right hlaf
5. Stop when the left index exceeds the right index
## Example
1. Search in Sorted Data (Databases, Logs)
2. Autocomplete & Dictionary Lookups
3. Video Streaming Youtube Seek Bar
4. Game Development - Pathfinding & AI
5. OS-Level Scheduling
6. Finance - Price Range Search
7. Networking - Packet routing/Lookup Tables
8. E-commerce - Filtered Search
9. Facial Recognition / Matching Systems
10. Binary Search in System Design