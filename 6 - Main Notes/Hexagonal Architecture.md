2026-04-14 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Architecture]]

# Hexagonal Architecture

## What is it?
Hexagonal Architecture, also known as Ports and Adapters, is a software design pattern that emphasizes separating the core logic of an application from external concerns like databases, user interfaces, and third-party services. This structure creates "ports" (interfaces) through which the application communicates with "adapters" (implementations), allowing for flexibility and easier testing.

## Why does it matter?
Using Hexagonal Architecture enables developers to change or replace external components without affecting the core business logic of the application. This separation enhances maintainability, allows for easier unit testing, and supports the idea of evolving technology stacks over time without massive rewrites of the business logic.

## Example
Imagine you are building an online store. The core logic is about processing orders and managing inventory. With Hexagonal Architecture, you might have an interface (port) for payment processing. You can create multiple adapters for different payment methods, like credit cards or PayPal. If you decide to switch from PayPal to Stripe, you only need to update the adapter without changing your core order processing code.

Here’s a simple Python example:

```python
class PaymentProcessor:
    def process_payment(self, amount):
        raise NotImplementedError

class PayPalAdapter(PaymentProcessor):
    def process_payment(self, amount):
        print(f"Processing ${amount} through PayPal.")

class StripeAdapter(PaymentProcessor):
    def process_payment(self, amount):
        print(f"Processing ${amount} through Stripe.")

# Usage
payment = PayPalAdapter()
payment.process_payment(100)
```

In this example, the `PaymentProcessor` is the port, while `PayPalAdapter` and `StripeAdapter` are two different ways to handle payments, demonstrating the flexibility of Hexagonal Architecture.