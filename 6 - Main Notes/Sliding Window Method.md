2025-08-19 22:45

Status:
Tag: [[Software Engineering]] [[Algorithms]] [[Sliding Window]] [[leetcode]]

# Sliding Window Method

## What is it?
Sliding Window is a technique to reduce nest loops into linear time solution when dealing with subarrays or substrings.

Instead of recalculating things from scratch for every subarray/substring, you reuse previous results and "slide" your window forward.

## When to use it?
Sliding window is typically used when
1. You're asked about subarrays/substrings (continuous elements)
2. The problem involves:
		- Fixed length window -> Find the max sum of any subarray of length k
		- Variable length window -> Find the smallest subarray that satisfies condition
		- Dynamic constraints -> Longest substring with at most k distinct characters

## Why does it matter?
If we were to use brute force to solve the problems we would re-check overlapping ranges
Sliding windows remembers what you already calculated and adjusts incrementally

## Example
If you're scanning through a sequence looking for the best/longest/shortest contiguous subarray/substring think sliding window