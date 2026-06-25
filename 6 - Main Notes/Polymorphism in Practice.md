2026-06-25 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Programming Fundamentals]]

# Polymorphism in Practice

## What is it?
Polymorphism is a fundamental concept in object-oriented programming (OOP) that allows methods to do different things based on the object that it is acting upon. In simpler terms, polymorphism enables a single interface to be used for different underlying forms (data types). This means that the same function name can be used for different types of objects, allowing for more flexible and reusable code.

## Why does it matter?
Polymorphism is important in software engineering because it promotes code reusability and scalability. By allowing objects to be treated as instances of their parent class, developers can write more generic code that works with multiple types. This can lead to cleaner code and a reduction in redundancy, making maintenance easier and enhancing collaboration among team members.

## Example
Here’s a simple example in Python:

```python
class Animal:
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Bark"

class Cat(Animal):
    def sound(self):
        return "Meow"

def make_sound(animal: Animal):
    print(animal.sound())

dog = Dog()
cat = Cat()

make_sound(dog)  # Output: Bark
make_sound(cat)  # Output: Meow
```

In this example, both `Dog` and `Cat` classes inherit from the `Animal` class and implement the `sound` method differently. The `make_sound` function can take any `Animal` and call its `sound` method, demonstrating polymorphism in action!