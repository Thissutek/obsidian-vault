2026-04-29 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Factory Pattern

## What is it?
The Factory Pattern is a design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created. Instead of calling a constructor directly, you call a factory method that returns an instance of the desired class. This promotes loose coupling in your code, making it easier to manage and extend.

## Why does it matter?
In real software engineering, the Factory Pattern is crucial for maintaining clean and scalable code. It allows developers to create objects without specifying the exact class of the object, enabling easier updates and modifications. When your application grows, you can add new classes without changing existing code, which reduces the risk of bugs and makes your codebase more flexible.

## Example
Here's a simple Python example of the Factory Pattern:

```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

class AnimalFactory:
    @staticmethod
    def create_animal(animal_type):
        if animal_type == 'dog':
            return Dog()
        elif animal_type == 'cat':
            return Cat()
        return None

# Usage
animal = AnimalFactory.create_animal('dog')
print(animal.speak())  # Output: Woof!
```

In this example, the `AnimalFactory` class creates instances of `Dog` and `Cat` without exposing the details of their instantiation. You can add more animal types later without modifying the client code.