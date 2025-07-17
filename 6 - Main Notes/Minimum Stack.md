2025-07-16 22:15

Status:
Tag: [[leetcode]] [[stack]]

# Minimum Stack

## Problem
Design a stack class that supports the `push`, `pop`, `top`, and `getMin` operations.

- `MinStack()` initializes the stack object.
- `void push(int val)` pushes the element `val` onto the stack.
- `void pop()` removes the element on the top of the stack.
- `int top()` gets the top element of the stack.
- `int getMin()` retrieves the minimum element in the stack.

Each function should run in O(1)O(1) time.

Example 
Input: ["MinStack", "push", 1, "push", 2, "push", 0, "getMin", "pop", "top", "getMin"]

Output: [null,null,null,null,0,null,2,1]

Explanation:
MinStack minStack = new MinStack();
minStack.push(1);
minStack.push(2);
minStack.push(0);
minStack.getMin(); // return 0
minStack.pop();
minStack.top();    // return 2
minStack.getMin(); // return 1

## Constraints
The constraint is when finding the minimum value if we were to check everything one at a time finding the minimum would take n times which would make it O(n) but the constraint is we need to design this so its O(1) speed.

An easy way to make this design is have the minimum number tracked every time a new number is pushed onto the stack so we would always have that value. So our stack would look like 
```
[val, minVal]
```

## Plan Pseudocode
```
Initialize the stack = []

push(val)
	if the stack is empty 
		stack.push([val, val])
	else 
		currentMin = stack[stack.length - 1][1]
		stack.push(val, min(val, currentMin))

pop()
	stack.pop()

top()
	return stack[stack.length - 1][0]

getMin()
	return stack[stack.length - 1][1]
```
## Solution

```
class MinStack {
  constructor() {
    this.stack = [];
  }

  push(val) {
    if (this.stack.length === 0) {
      this.stack.push([val, val]);
    } else {
      const currentMin = this.getMin();
      this.stack.push([val, Math.min(val, currentMin)]);
    }
  }

  pop() {
    this.stack.pop();
  }

  top() {
    return this.stack[this.stack.length - 1][0];
  }

  getMin() {
    return this.stack[this.stack.length - 1][1];
  }
}

```

### Takeaway
Why I was getting stuck first i forgot about constructs specifically with calling the **this** keyword. Also something I was having trouble grasping is when looking at the top and getMin we can see in the first index it calls the end of the stack which is the latest value that was pushed. I think I'm just struggling with why its necessary when all we need is the specific val for those functions but because the stack is in a pair value it would be called for that.