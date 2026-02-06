2025-08-07 15:25

Status:
Tag: [[Binary Search]] [[leetcode]]
Difficulty: #medium
# Search a 2D Matrix
## Problem
You are given an `m x n` 2-D integer array `matrix` and an integer `target`.

- Each row in `matrix` is sorted in _non-decreasing_ order.
- The first integer of every row is greater than the last integer of the previous row.

Return `true` if `target` exists within `matrix` or `false` otherwise.

Can you write a solution that runs in `O(log(m * n))` time?

**Example 1:**

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/7ca61f56-00d4-4fa0-26cf-56809028ac00/public)

```java
Input: matrix = [[1,2,4,8],[10,11,12,13],[14,20,30,40]], target = 10

Output: true
```

**Example 2:**

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/f25f2085-ce04-4447-9cee-f0a66c32a300/public)

```java
Input: matrix = [[1,2,4,8],[10,11,12,13],[14,20,30,40]], target = 15

Output: false
```

**Constraints:**

- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 100`
- `-10000 <= matrix[i][j], target <= 10000`

## Constraints
- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 100`
- `-10000 <= matrix[i][j], target <= 10000`


## My Thoughts
Well the first thought is even though its in a 2D Matrix and if we look at the total numbers and not separated into 3 arrays all the numbers are sorted from lowest to highest its just a matter of applying binary search to find the number and if it doesn't exist.

## Plan Pseudocode
```
Function searchMatrix(matrix, target) {
	if matrix is empty or matrix[0] is empty 
		return false

	m = number of rows in matrix
	n = number of cols in matrix

	left = 0
	right = m * n - 1
	while left <= right:
		mid = floor((left + right) / 2)

		row = floor(mid/ n )
		col = mid % n 
		value = matrix[row][col]

		if (value === target): 
			return true
		else if value < target:
			left = mid + 1
		else
			right = mid - 1

	return false // target not found
}

```

## Solution
```
class Solution {

/**

* @param {number[][]} matrix

* @param {number} target

* @return {boolean}

*/

searchMatrix(matrix, target) {

	if(matrix.length === 0 || matrix[0].length === 0) {

	return false;

}
	let m = matrix.length;
	let n = matrix[0].length;

	let left = 0;
	let right = m * n - 1;
	
	while (left <= right) {
		let mid = Math.floor((left + right)/ 2);
		let row = Math.floor(mid / n);
		let col = mid % n;
		let value = matrix[row][col];

		if(value === target) {
			return true
		} else if (value < target) {
			left = mid + 1;
		} else {
			right = mid - 1
		}
	}
return false;
}
}
```

## Notes
Reading through the code makes a lot of sense first we check if the matrix is empty and also if the array inside is empty or not. Then we have the values of m and n which represents how many numbers are in the each array and how many arrays are there in total. Then we have two pointers one at the beginning and one at the end which would be the m * n - 1 because we can think of like a square to get the full amount we multiple i guess the length and width. then we find the values of mid point but we also have to check which row and col and we have to also check value inside it so it all makes sense on paper like I can read this and understand and then we add the checks at the end to make sure its the actual target number we are looking for and the left and right in the if statements are basically the halves of each side so when we know the target is bigger than the value than we move the left marker to the middle of the array but plus 1 cause we already checked it and right if the value is less than the target so we get the mid and go left so minus 1. 
