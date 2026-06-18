2026-06-18 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Design Patterns]]

# Strangler Fig Pattern

## What is it?
The Strangler Fig Pattern is a software development strategy used to gradually replace or refactor an existing system with a new one. It involves building new features in the new system while allowing the old system to coexist until the transition is complete, much like how a strangler fig tree grows around an existing tree, eventually taking its place.

## Why does it matter?
This pattern is important as it allows for a smoother transition from legacy systems to modern architectures without needing a complete rewrite, which can be risky and costly. It enables teams to incrementally improve the system, reduce downtime, and minimize disruption, all while continuously delivering value to users.

## Example
Imagine you're updating an old e-commerce platform. Instead of rewriting the entire system at once, you can start by developing a new checkout feature in a modern architecture. The new checkout can call the old system for product details while you gradually build new functionality around it. This way, customers can still use the old system, and you can slowly replace other components until the entire platform is modernized. 

Here’s a simplified example in Python:

```python
# Old system checkout function
def old_checkout(order):
    print("Processing order in legacy system:", order)

# New system checkout function
def new_checkout(order):
    print("Processing order in new system:", order)

# Strangler Fig approach
def checkout(order, use_new_system=False):
    if use_new_system:
        new_checkout(order)
    else:
        old_checkout(order)

# Example usage
checkout("Order #123", use_new_system=True)  # Calls the new system
checkout("Order #124", use_new_system=False)  # Calls the old system
```