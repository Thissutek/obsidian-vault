2026-04-21 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Adapter Pattern

## What is it?
The Adapter Pattern is a design pattern that enables incompatible interfaces to work together. It acts as a bridge between two different systems, allowing them to communicate without modifying their existing code. Essentially, it wraps one interface and translates its calls to another interface that the client can understand.

## Why does it matter?
In real software engineering, applications often need to integrate with external libraries or systems that may not match the desired interface. The Adapter Pattern helps developers to incorporate these components seamlessly, promoting code reuse and reducing the need for extensive rewrites. This can save time and resources, making your software more flexible and easier to maintain.

## Example
Imagine you have a legacy payment system that accepts payments in dollars, but you want to integrate it with a new payment service that uses euros. Instead of rewriting the entire payment system, you can create an adapter:

```python
class LegacyPaymentSystem:
    def pay_in_dollars(self, amount):
        print(f"Paying ${amount}.")

class EuroPaymentAdapter:
    def __init__(self, legacy_system):
        self.legacy_system = legacy_system

    def pay_in_euros(self, amount):
        dollars = amount * 1.1  # Assume 1 Euro = 1.1 Dollars
        self.legacy_system.pay_in_dollars(dollars)

# Usage
legacy_system = LegacyPaymentSystem()
adapter = EuroPaymentAdapter(legacy_system)
adapter.pay_in_euros(100)  # This will convert 100 Euros to dollars and process the payment.
```

In this example, the `EuroPaymentAdapter` allows the new service to interact with the existing `LegacyPaymentSystem`, demonstrating how the Adapter Pattern works in practice.