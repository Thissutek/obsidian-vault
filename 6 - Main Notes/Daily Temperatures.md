2025-07-17 22:33

Status:
Tag: [[stack]] [[leetcode]] [[Data Structure Stacks]] [[Monotonic Stack Problem]]
Difficulty: Medium 
# Daily Temperatures
## Problem
You are given an array of integers `temperatures` where `temperatures[i]` represents the daily temperatures on the `ith` day.

Return an array `result` where `result[i]` is the number of days after the `ith` day before a warmer temperature appears on a future day. If there is no day in the future where a warmer temperature will appear for the `ith` day, set `result[i]` to `0` instead.

**Example 1:**

```java
Input: temperatures = [30,38,30,36,35,40,28]

Output: [1,4,1,2,1,0,0]
```

**Example 2:**

```java
Input: temperatures = [22,21,20]

Output: [0,0,0]
```

## Constraints
- `1 <= temperatures.length <= 1000`.
- `1 <= temperatures[i] <= 100`

## My Thoughts
First, I'm trying to figure out and break down what exactly the question is asking me. I get it the question is asking so for the current index of the array which is also the 'ith' day they want me to keep track of how many days in between the current index to the next index which has a high value and return that number in the index.

First we would need to go through each number in the array each index, so lets say I'm on index [0] I need to have something that like a for loop to check the next number in the sequence and compare if its bigger we end that sequence and return that number for where the index is if not and the number isn't bigger we go to the next number and increase the amount of days so far so it would be 2. 

I don't think its efficient to use two for loops that sounds kind of weird and not efficient. I would assume it would be backtracking and we would keep adding to the stack until we come across a number that is bigger than the current index that we have 

## Plan Pseudocode
```
Initialize result array filled with 0s
Initialize empty stack (to hold indices)

For i from 0 to temperatures.length - 1:
    While stack is not empty AND temperatures[i] > temperatures[stack top]:
        prevIndex = stack.pop()
        result[prevIndex] = i - prevIndex
    Push i onto stack
```

## Solution
```
dailyTemperatures(temperatures) {
	const result = new Array(temperatures.length).fill(0);
	const stack = [];

	for(let i = 0; i < temperatures.length; i++) {

		while(stack.length && temperatures[i] > temperatures[stack[stack.length - 1]]) {
		const prevIndex = stack.pop();
		result[prevIndex] = i - prevIndex;
	}
	stack.push(i);
}
return result;
}
```

## Notes
[[Monotonic Stack Problem]]

I understand the logic of the problem its always usually just translating it to code. I think the thing is try to understand the pseudocode as much as possible that will be where the logic and function will be. 