2026-06-30 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# DRY Principle

## What is it?
The DRY principle stands for "Don't Repeat Yourself." It's a software development concept that emphasizes reducing the duplication of code and logic within a program. Instead of writing the same code in multiple places, developers should create reusable functions or components, making code more efficient and easier to maintain.

## Why does it matter?
The DRY principle is crucial in real software engineering because it minimizes the risk of errors and inconsistencies that can arise when changes are made to duplicated code. When updates are needed, having the code in one place means you only need to make the change once, saving time and reducing the potential for bugs. This leads to cleaner, more organized codebases that are easier for teams to understand and modify.

## Example
Here’s a simple example in Python:

```python
def calculate_area(length, width):
    return length * width

# Instead of repeating the calculation
area1 = 5 * 10
area2 = 7 * 12

# Use the DRY principle
area1 = calculate_area(5, 10)
area2 = calculate_area(7, 12)
```

In this example, the area calculation is encapsulated in a function, allowing you to reuse it without repeating the multiplication logic.