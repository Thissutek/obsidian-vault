2025-07-17 16:49

Status:
Tag:[[stack]] [[Data Structure Stacks]] [[leetcode]]
Difficulty: #medium

# Generate Parentheses
## Problem
You are given an integer `n`. Return all well-formed parentheses strings that you can generate with `n` pairs of parentheses.

**Example 1:**

```java
Input: n = 1

Output: ["()"]
```

**Example 2:**

```java
Input: n = 3

Output: ["((()))","(()())","(())()","()(())","()()()"]
```

You may return the answer in **any order**.

## Constraints
- `1 <= n <= 7`

## Thought Process
First assumption is what makes a valid parentheses it looks like it always as to start with a open bracket. Second we need to return all the variations of the parentheses so backtracking is involved which is what the stack is for. Last the int that is given it will always be double cause parentheses come in pairs 


## Plan Pseudocode
```
Define backtrack(currString, leftCount, rightCount):

    If currString is complete (length === 2 * n):
        Add currString to result
        Return

    If leftCount < n:
        backtrack(currString + "(", leftCount + 1, rightCount)

    If rightCount < leftCount:
        backtrack(currString + ")", leftCount, rightCount + 1)
```

## Solution

```
function generateParenthese(n) {
	let result = []
	function backtrack(curr, left, right) {
		if(curr.length === n * 2) {
			result.push(curr)
			return;
		}
		if(left < n) {
			backtrack(curr + '(',  left + 1, right )
		}
		if(right < left) {
			backtrack(curr + ')', left, right + 1)
		}
	}
	backtrack("",0, 0)
	return result
}
```

## Notes
so for this I get it I can't really imagine this exactly like in a imagine form but I get the logic, it kind of came simple to me sorta of like I'll look at the code solution and I can do it within the code editor without referring back to it which is good I think the progress is there cause I feel like I'm thinking too methodically and I just need to think about the actions that the function takes. 