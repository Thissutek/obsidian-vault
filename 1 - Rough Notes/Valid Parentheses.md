2025-07-10 21:02

Status:

Tags: [[leetcode]] [[stack]]

## Valid Parentheses
Problem is you are given a string of brackets they are only true if they have a closing bracket but in the order of the stack if they are out of the order of the stack even though its a closing bracket it will result in false

Simple problem using the stack data structure. This first has stack array this keeps track of the plates, in the map that basically makes the key value pairs so for each each bracket there should be closed one

The for loop goes through the string which is s this would be a series of brackets the char constant is the current string we are on if the char is in the map and if the stack is 0 or we are at the end of the stack and its the char then we can return false then that means the string is invalid. 

if it isn't invalid then we are going to take the return the last remove the last element or else we are going to push that char into the stack cause thats the start of the brackets

lastly if everything is passed we will have the stack = 0 which means it is true

```
class Solution {

isValid(s) {

	let stack = [];
	const map = {
	')': '(',
	']': '[',
	'}': '{'
	}
	for(let i = 0; i < s.length; i++) {
		const char = s[i]
		if (map[char]) {
		if (stack.length === 0 || stack[stack.length - 1] !== map[char]) {
			return false;
		}
			stack.pop();
		} else {
			stack.push(char);
		}
	}
	return stack.length === 0;
	}
}
```

## References 