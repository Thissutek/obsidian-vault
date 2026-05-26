2026-05-26 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Strategy Pattern

## What is it?
The Strategy Pattern is a behavioral design pattern that enables selecting an algorithm's behavior at runtime. It allows you to define a family of algorithms, encapsulate each one, and make them interchangeable. This way, the algorithm can vary independently from clients that use it.

## Why does it matter?
In software engineering, the Strategy Pattern promotes flexibility and reuse of code by allowing changes to be made without modifying existing code. This is particularly useful when your application needs to support multiple algorithms or behaviors, as it helps avoid code duplication and enhances maintainability. It's a great way to keep your code clean and adaptable to future changes.

## Example
Here's a simple example in Python demonstrating the Strategy Pattern:

```python
class PaymentStrategy:
    def pay(self, amount):
        pass

class CreditCardPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paid {amount} using Credit Card.")

class PayPalPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paid {amount} using PayPal.")

class ShoppingCart:
    def __init__(self, payment_strategy):
        self.payment_strategy = payment_strategy

    def checkout(self, amount):
        self.payment_strategy.pay(amount)

# Usage
cart = ShoppingCart(CreditCardPayment())
cart.checkout(100)  # Output: Paid 100 using Credit Card.
```

In this example, you can easily switch between payment methods (strategies) without altering the `ShoppingCart` class, illustrating the flexibility the Strategy Pattern provides.