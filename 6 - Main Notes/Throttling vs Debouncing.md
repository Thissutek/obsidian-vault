2026-03-13 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Throttling vs Debouncing

## What is it?
Throttling and debouncing are techniques used to control how often a function gets executed, especially when it's triggered by events like scrolling or resizing the window. Throttling ensures a function runs at regular intervals, while debouncing postpones execution until a certain period of inactivity has passed.

## Why does it matter?
These techniques are important for optimizing performance in web applications. Without them, a function could be called too many times in rapid succession, leading to slow performance or excessive resource usage. For instance, during a window resize event, running a function too frequently can cause significant lag; throttling or debouncing can smooth out the experience for users.

## Example
Here’s a simple example in JavaScript to show how throttling can limit function calls:

```javascript
let lastExecution = 0;

function throttle(func, limit) {
  return function() {
    const now = Date.now();
    if (now - lastExecution >= limit) {
      lastExecution = now;
      func.apply(this, arguments);
    }
  };
}

window.addEventListener('resize', throttle(() => {
  console.log('Window resized!');
}, 200));
```

In this example, the `throttle` function ensures that the message "Window resized!" is logged at most every 200 milliseconds, even if the window is resized continuously.