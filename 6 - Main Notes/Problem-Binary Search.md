2025-07-30 16:50

Status:
Tag: [[Binary Search]] [[leetcode]]
Difficulty: #easy 
# Problem-Binary Search
## Problem
You are given an array of **distinct** integers `nums`, sorted in ascending order, and an integer `target`.

Implement a function to search for `target` within `nums`. If it exists, then return its index, otherwise, return `-1`.

Your solution must run in O(logn)O(logn) time.

**Example 1:**

```java
Input: nums = [-1,0,2,4,6,8], target = 4

Output: 3
```

**Example 2:**

```java
Input: nums = [-1,0,2,4,6,8], target = 3

Output: -1
```

## Constraints

- `1 <= nums.length <= 10000`.
- `-10000 < nums[i], target < 10000`
- All the integers in `nums` are **unique**.

## My Thoughts
This is the base line default of how it works. So first thing is the array is already sorted which is good, we find the middle of the array and we check if the target number matches if its smaller we check the left if its larger we check the right. We find the middle of the left or right and we do the same check again. 

## Plan Pseudocode
```
function binarySearch(nums, target) {
	left = 0
	right = nums.length - 1

	while left < = right 
		mid = floor((left + right) /2)
	if nums[mid] == target
		return mid
	else if target < nums[mid]
		right = mid - 1
	else
		left = mid + 1
return -1
}
```

## Solution
```
class Solution {

/**

* @param {number[]} nums

* @param {number} target

* @return {number}

*/

search(nums, target) {}
	let left = 0;
	let right = nums.length - 1;

	while (left <= right) {
		let mid = Math.floor((left + right) / 2);
		
		if (nums[mid] === target) {
			return mid 
		} else if (target < nums[mid]) {
			right = mid - 1;
		} else {
			left = mid +1
		}
	}
	return -1;
}
```

## Notes
Simple concept to understand, I remember this algorithm in my earlier days of learning computer science its a good refresher especially having not spent any time leetcoding recently, I need more practice with the just structuring my solution I ended up using the AI to help with pseudocode but from pseudocode I was able to make the actual working code so I need more practice with just planning it in pseudo.