2025-07-18 15:48

Status:
Tag: [[stack]] [[Data Structure Stacks]] [[leetcode]]
Difficulty: #medium 
# Car Fleet
## Problem
There are `n` cars traveling to the same destination on a one-lane highway.

You are given two arrays of integers `position` and `speed`, both of length `n`.

- `position[i]` is the position of the `ith car` (in miles)
- `speed[i]` is the speed of the `ith` car (in miles per hour)

The **destination** is at position `target` miles.

A car can **not** pass another car ahead of it. It can only catch up to another car and then drive at the same speed as the car ahead of it.

A **car fleet** is a non-empty set of cars driving at the same position and same speed. A single car is also considered a car fleet.

If a car catches up to a car fleet the moment the fleet reaches the destination, then the car is considered to be part of the fleet.

Return the number of **different car fleets** that will arrive at the destination.

**Example 1:**

```java
Input: target = 10, position = [1,4], speed = [3,2]

Output: 1
```

Explanation: The cars starting at 1 (speed 3) and 4 (speed 2) become a fleet, meeting each other at 10, the destination.

**Example 2:**

```java
Input: target = 10, position = [4,1,0,7], speed = [2,2,1,1]

Output: 3
```

Explanation: The cars starting at 4 and 7 become a fleet at position 10. The cars starting at 1 and 0 never catch up to the car ahead of them. Thus, there are 3 car fleets that will arrive at the destination.

## Constraints
- `n == position.length == speed.length`.
- `1 <= n <= 1000`
- `0 < target <= 1000`
- `0 < speed[i] <= 100`
- `0 <= position[i] < target`
- All the values of `position` are **unique**.

## My Thoughts
There are a couple parts to this question, first position and speed the same index for both is one car so speed[0] and position[0] is one of the cars and whatever value is there determines the speed and position.

Other constraints cars can't pass it each other they can only be in the same position and drive at the same speed so once a car catches up their speed changes into that of the car driving with it.

Car fleet is the goal single car can be a fleet so the goal seems to be like when there are different fleets at different speeds and positions even if the car is only one how many of those unique fleets will meet the target. 

My first thought is first creating a variable like car that has position[0] speed[0] and those have values correct when the speed increases the position but if that position is either equal to or greater to that of the cars in the array it would take on that cars properties position and speed and become a fleet. 


## Plan Pseudocode
```
Initialize cars as list of (position, speed) pairs

Sort cars by position descending

Initialize empty stack (to keep track of fleet times)

For each car in cars:

    time = (target - position) / speed

    If stack is empty OR time > stack top:
        Push time onto stack  // New fleet formed
    Else:
        // Car joins the fleet in front (no push)

Return stack size as the number of fleets
```

## Solution
```
class Solution {

carFleet(target, position, speed) {
	const n = position.length;
	if (n === 0) return 0;

	// Step 1: Pair each car's position and speed
	const cars = [];
	for(let i = 0; i < n; i++) {
		cars.push([position[i], speed[i]]);
	}

	// Step 2. Sort cars by position descending closest to the target first
	cars.sort((a, b) => b[0] -a[0]);

	// Step.3 Use a stack to track fleets
	const stack = [];

	for (let i = 0; i < n; i++) {
		const [pos, spd] = cars[i];
		const time = (target - pos) / spd;

		// If the current car can't catch up to the fleet in front new fleet

		if (stack.length === 0 || time > stack[stack.length - 1]) {
		stack.push(time)
		}
	}
	return stack.length;
}

}
```


## Notes
Breaking down the problem made it seem like was easier than it is. Its a medium difficulty question the thing about it is I need sort of only understand it like why its doing it but im still thinking about how the stack works in this case 

|Step|What’s Happening|
|---|---|
|Sort cars|Setup who’s in front|
|Calculate time|Determine who will finish first|
|Stack push|New fleet|
|Stack ignore|Car joins existing fleet|