2026-03-15 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Singleton Pattern

## What is it?
The Singleton Pattern is a design pattern that restricts a class to a single instance and provides a global point of access to that instance. It ensures that no more than one object is created from the class, which is particularly useful when exactly one object is needed to coordinate actions across the system.

## Why does it matter?
The Singleton Pattern is important because it helps manage shared resources, such as database connections or configuration settings, without the complexity of creating multiple instances. It also helps in controlling access to these resources, improving performance and reducing memory usage in applications where a single instance suffices.

## Example
Here’s a simple Python example of the Singleton Pattern using a class that ensures only one instance is created:

```python
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance

# Usage
singleton1 = Singleton()
singleton2 = Singleton()

print(singleton1 is singleton2)  # Output: True
```
In this example, both `singleton1` and `singleton2` refer to the same instance of `Singleton`, demonstrating that only one instance exists, regardless of how many times the class is instantiated.