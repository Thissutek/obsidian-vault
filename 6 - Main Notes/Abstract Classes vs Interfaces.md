2026-06-04 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Programming Fundamentals]]

# Abstract Classes vs Interfaces

## What is it?
Abstract classes and interfaces are both used in object-oriented programming to define abstract types that can be shared by different classes. An abstract class can have both defined methods (with code) and abstract methods (without code), while an interface only defines methods without any implementation, meaning the implementing classes must provide the actual code. 

## Why does it matter?
Understanding the difference between abstract classes and interfaces is crucial for designing flexible and reusable code. Abstract classes allow for shared behavior and state, while interfaces enforce a contract that multiple classes can follow, promoting a consistent API. This distinction helps keep your code organized and maintainable, especially in large projects with multiple developers.

## Example
Here's a simple example in Python that demonstrates both concepts:

```python
from abc import ABC, abstractmethod

# Abstract class
class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

    def eat(self):
        return "Eating..."

# Interface-like class using abstract methods
class CanFly(ABC):
    @abstractmethod
    def fly(self):
        pass

# Concrete class implementing both
class Bird(Animal, CanFly):
    def sound(self):
        return "Chirp!"
    
    def fly(self):
        return "Flying high!"

# Usage
bird = Bird()
print(bird.sound())  # Output: Chirp!
print(bird.eat())    # Output: Eating...
print(bird.fly())    # Output: Flying high!
```

In this example, `Animal` is an abstract class that has a concrete method `eat()` and an abstract method `sound()`. The `CanFly` class acts like an interface with an abstract method `fly()`, which `Bird` implements, showcasing both concepts in action.