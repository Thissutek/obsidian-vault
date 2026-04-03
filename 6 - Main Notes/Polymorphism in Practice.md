2026-04-03 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Programming Fundamentals]]

# Polymorphism in Practice

## What is it?
Polymorphism is a concept in programming that allows objects of different classes to be treated as objects of a common superclass. The two main types of polymorphism are compile-time (or static) polymorphism, which is achieved through method overloading, and runtime (or dynamic) polymorphism, which is achieved through method overriding.

## Why does it matter?
Polymorphism enhances code reusability and flexibility. By allowing one interface to control access to different underlying forms (data types), it makes it easier to write code that can work with new classes that you might add later. This leads to cleaner, more maintainable code, as you don't need to change the existing code every time you introduce a new class.

## Example
Here’s a simple example in Python demonstrating runtime polymorphism using method overriding:

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

def animal_sound(animal):
    print(animal.speak())

dog = Dog()
cat = Cat()

animal_sound(dog)  # Output: Woof!
animal_sound(cat)  # Output: Meow!
```

In this example, both `Dog` and `Cat` classes inherit from `Animal`. The `speak` method is overridden in each subclass, allowing us to call the same method on different objects and get different results.