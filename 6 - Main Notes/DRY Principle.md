2026-02-28 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Software Principles]]

# DRY Principle

## What is it?
The DRY Principle stands for "Don't Repeat Yourself." It's a fundamental programming concept that encourages developers to reduce duplication in their code by abstracting repeated pieces of logic into a single, reusable component. Essentially, if you find yourself copying and pasting code, it's a sign that you should refactor it into a function or a class.

## Why does it matter?
The DRY principle is crucial because it leads to cleaner, more maintainable code. When code is duplicated, any changes need to be made in multiple places, increasing the risk of bugs and inconsistencies. By following DRY, you make your code easier to read and modify, which ultimately saves time and reduces errors in the long run.

## Example
Here's a simple example in Python to illustrate the DRY principle:

```python
def calculate_area(length, width):
    return length * width

# Instead of repeating the area calculation:
area1 = 10 * 5
area2 = 20 * 15

# Use the function to avoid repetition:
area1 = calculate_area(10, 5)
area2 = calculate_area(20, 15)
```

In this example, instead of repeating the multiplication for calculating the area, we create a function `calculate_area`. This way, if we need to change how we calculate the area later, we only have to update it in one place!