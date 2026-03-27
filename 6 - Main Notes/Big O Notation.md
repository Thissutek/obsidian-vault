2026-03-27 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Algorithms]]

# Big O Notation

## What is it?
Big O Notation is a mathematical notation used to describe the performance or complexity of an algorithm. Specifically, it expresses the relationship between the size of the input and the time or space required by the algorithm, focusing on the worst-case scenario. In simple terms, it allows us to evaluate how the runtime of an algorithm increases as the input size grows.

## Why does it matter?
Understanding Big O Notation is crucial for software engineers because it helps us make informed decisions about which algorithms to use in our applications. By evaluating the efficiency of different approaches, we can optimize performance, especially in applications that handle large amounts of data or require quick response times. This knowledge ultimately leads to more scalable and efficient software solutions.

## Example
Here’s a simple example in Python that illustrates Big O Notation:

```python
def find_max(numbers):
    max_num = numbers[0]  # O(1), constant time
    for num in numbers:    # O(n), linear time
        if num > max_num:
            max_num = num
    return max_num
```

In this code, the `find_max` function has a time complexity of O(n) because it needs to look at each number in the list to find the maximum value. As the number of elements in the list increases, the time taken will increase linearly.