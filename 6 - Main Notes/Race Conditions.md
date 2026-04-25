2026-04-25 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Race Conditions

## What is it?
A race condition occurs in software when two or more processes or threads attempt to change shared data at the same time, leading to unpredictable outcomes. It happens because the sequence of execution can affect the final state of the data, causing bugs that are difficult to replicate and fix.

## Why does it matter?
Race conditions are critical to understand because they can lead to data corruption, crashes, or unexpected behavior in applications. This is especially important in multi-threaded or distributed systems where tasks are executed concurrently. If not managed properly, race conditions can compromise the integrity and reliability of the software, impacting user trust and leading to costly downtimes.

## Example
Consider a simple banking system where two transactions try to update the same account balance simultaneously:

```python
balance = 100

def deposit(amount):
    global balance
    temp = balance
    temp += amount
    balance = temp

# Transaction 1: deposit 50
# Transaction 2: deposit 30
```

If both transactions run at the same time without proper management (like locks), they might read the same initial balance (`100`) and both end up setting the balance to `150` instead of the correct `180`. This shows how race conditions can lead to incorrect results if access to shared resources is not synchronized.