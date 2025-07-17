2025-07-17 15:50

Status:
Tag: [[stack]] [[leetcode]] [[Data Structure Stacks]]

# Evaluate Reverse Polish Notation
## Problem
You are given an array of strings `tokens` that represents a **valid** arithmetic expression in [Reverse Polish Notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation).

Return the integer that represents the evaluation of the expression.

- The operands may be integers or the results of other operations.
- The operators include `'+'`, `'-'`, `'*'`, and `'/'`.
- Assume that division between integers always truncates toward zero.

**Example 1:**

```java
Input: tokens = ["1","2","+","3","*","4","-"]

Output: 5

Explanation: ((1 + 2) * 3) - 4 = 5
```

**Constraints:**

- `1 <= tokens.length <= 1000`.
- tokens[i] is `"+"`, `"-"`, `"*"`, or `"/"`, or a string representing an integer in the range `[-100, 100]`.

## Constraints
- `1 <= tokens.length <= 1000`.
- tokens[i] is `"+"`, `"-"`, `"*"`, or `"/"`, or a string representing an integer in the range `[-100, 100]`.
## Analyzing
So what is RPN Reverse Polish Notation is when the operator (+, -, /, x) comes after the number so if I have (1, 2, +). it would be 1 + 2 you are basically taking the the last two numbers and applying whatever the operator is. This would be perfect for the stack so we push any two numbers and if the next thing thats gets pushed onto the stack is an operator you just pop off the last two and use the operation. Sounds easy in theory, in code might be different to imagine

## Plan Pseudocode
```
Initialize the stack 

For each token in the input: 
	if token is a number: 
		push it onto stack
	else 
		pop second number (x)
		pop first number (y)
		Compute a operator x
		Push result back onto the stack
return stack[0]
```
## Solution
```
function evalRPN(tokens) {
  const stack = [];

  for (const token of tokens) {
    if (["+", "-", "*", "/"].includes(token)) {
      const b = stack.pop();
      const a = stack.pop();

      let result;
      switch (token) {
        case "+": result = a + b; break;
        case "-": result = a - b; break;
        case "*": result = a * b; break;
        case "/": 
          result = Math.trunc(a / b); // Truncate toward zero
          break;
      }

      stack.push(result);
    } else {
      stack.push(Number(token));
    }
  }

  return stack[0];
}

```

## Analyzing the solution
So we can see in this we basically use a for loop to check every item in token I always forget that this is a way to use for loops. If I used the traditional way it would probably work the same but the language for this one is a lot easier let like numbers for the for loop it just checks for each index in the given input since in the input is an array.

now that first if statement is there if we just started the function it would skip that first if because we don't have anything in the stack yet
we also initialize the result to a empty number so we just have the variable and we pass through the switch statement so we can have the result that it outputs otherwise we are going to push the number or what the token is to the stack and it repeats. 

Its very smart way of handling the logic for this. 