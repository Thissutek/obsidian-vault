2026-06-06 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Mutexes and Semaphores

## What is it?
Mutexes (short for Mutual Exclusion) and Semaphores are synchronization primitives used in programming to manage access to shared resources. A mutex allows only one thread to access a resource at a time, effectively locking it for other threads. Semaphores, on the other hand, can allow a limited number of threads to access a resource simultaneously, enabling more flexible control over resource access.

## Why does it matter?
In real software engineering, especially in multi-threaded applications, managing access to shared resources is crucial to prevent data corruption and ensure the correct functioning of the application. Without proper synchronization using mutexes or semaphores, you may encounter race conditions, where threads compete unexpectedly, leading to unpredictable behavior. This is especially important in scenarios like banking systems or online shopping, where accurate data processing is vital.

## Example
Here's a simple example in Python using a mutex:

```python
import threading

# Create a mutex
mutex = threading.Lock()
shared_resource = 0

def safe_increment():
    global shared_resource
    mutex.acquire()  # Lock the resource
    shared_resource += 1
    mutex.release()  # Unlock the resource

# Create multiple threads
threads = [threading.Thread(target=safe_increment) for _ in range(10)]
for thread in threads:
    thread.start()
for thread in threads:
    thread.join()

print(shared_resource)  # Output should be 10, ensures safe access
```

In this example, the mutex ensures that only one thread can increment the `shared_resource` at a time, preventing data corruption.