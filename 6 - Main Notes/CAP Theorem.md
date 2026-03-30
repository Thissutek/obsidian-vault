2026-03-30 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# CAP Theorem

## What is it?
The CAP Theorem, also known as Brewer's Theorem, states that in a distributed data system, you can only achieve two out of the following three guarantees: Consistency, Availability, and Partition Tolerance. Consistency means every read returns the latest write, Availability ensures that every request receives a response (even if it's not the most recent data), and Partition Tolerance allows the system to continue operating despite network failures that split the system into segments.

## Why does it matter?
Understanding the CAP Theorem is crucial for engineers designing distributed systems, like databases or cloud applications. It helps you make informed trade-offs between how data is handled and accessed during network issues, ensuring that you build systems that meet your users' expectations based on the specific needs of your application.

## Example
Imagine a bank's online system as a distributed database. If you prioritize **Consistency** and **Partition Tolerance** during a network split, users may be unable to access their account information (low availability). However, if you choose **Availability** and **Partition Tolerance**, users might see outdated balances, which can be problematic. Here's a simple illustration in Python:

```python
class BankAccount:
    def __init__(self):
        self.balance = 1000

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            return True
        return False

# Simulating network partition
account1 = BankAccount()
account2 = BankAccount()

# Account withdrawal in separate parts of a network
account1.withdraw(200)  # Consistent update?
print(account2.balance)  # Might not reflect the updated balance!
```

In this example, if `account2` operates without being aware of changes in `account1`, it reflects the challenges of consistency during a network split.