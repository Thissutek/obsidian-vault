2026-06-01 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Iterator Pattern

## What is it?
The Iterator Pattern is a design pattern that allows sequential access to elements in a collection without exposing the underlying structure of the collection. This means you can traverse a collection (like a list or a set) one element at a time, making it easier to work with data without needing to know how it's organized.

## Why does it matter?
Using the Iterator Pattern is important because it promotes a clean separation between the collection and the way elements are accessed. This enhances code maintainability and flexibility, allowing developers to change the underlying data structure without affecting the code that uses it. It also simplifies operations like looping through data, which can lead to more readable and efficient code.

## Example
Here’s a simple example in Python demonstrating the Iterator Pattern using a custom collection of names:

```python
class NameCollection:
    def __init__(self):
        self.names = []
        
    def add_name(self, name):
        self.names.append(name)
        
    def __iter__(self):
        return iter(self.names)

# Using the NameCollection
collection = NameCollection()
collection.add_name("Alice")
collection.add_name("Bob")

for name in collection:
    print(name)
```

In this code, `NameCollection` encapsulates a list of names, and the `__iter__` method allows iteration over the names without revealing how they are stored. When we use a `for` loop, it automatically handles the iteration thanks to the Iterator Pattern!