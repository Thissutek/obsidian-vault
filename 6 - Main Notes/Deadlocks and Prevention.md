2026-02-26 01:08

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Deadlocks and Prevention

## What is it?
A deadlock is a situation in computer systems where two or more processes cannot proceed because each is waiting for the other to release a resource. For example, if Process A holds Resource 1 and waits for Resource 2, while Process B holds Resource 2 and waits for Resource 1, they are stuck in a deadlock.

## Why does it matter?
Deadlocks can severely impact application performance and user experience, as they halt processes and prevent the system from performing tasks efficiently. Understanding and preventing deadlocks is crucial in software engineering to ensure systems are robust and can handle multiple processes concurrently without getting stuck.

## Example
Consider a scenario with two threads trying to access two resources, A and B:

```python
import threading

def thread1():
    lock_A.acquire()
    print("Thread 1 acquired lock A")
    lock_B.acquire()  # May lead to deadlock if thread 2 holds lock B
    print("Thread 1 acquired lock B")
    lock_B.release()
    lock_A.release()

def thread2():
    lock_B.acquire()
    print("Thread 2 acquired lock B")
    lock_A.acquire()  # May lead to deadlock if thread 1 holds lock A
    print("Thread 2 acquired lock A")
    lock_A.release()
    lock_B.release()

lock_A = threading.Lock()
lock_B = threading.Lock()

t1 = threading.Thread(target=thread1)
t2 = threading.Thread(target=thread2)
t1.start()
t2.start()
```

In this example, if both threads run simultaneously, they could end up waiting for each other indefinitely, causing a deadlock. To prevent this, you could enforce a strict order for acquiring locks.