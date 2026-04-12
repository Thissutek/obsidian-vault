2026-04-12 09:31

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Deadlocks and Prevention

## What is it?
A deadlock is a situation in programming where two or more processes are unable to proceed because each is waiting for the other to release resources. Imagine two people holding a piece of string, each pulling in opposite directions; neither can move without letting go of the string.

## Why does it matter?
Deadlocks are critical to understand in software engineering because they can lead to a complete halt in system operations, causing slowdowns or crashes. Preventing deadlocks ensures that your programs are more efficient and reliable, especially in multi-threaded applications where multiple processes may compete for shared resources.

## Example
Here's a simple example in Python that can lead to a deadlock situation:

```python
import threading

# Resources
resource_a = threading.Lock()
resource_b = threading.Lock()

def thread1():
    with resource_a:
        print("Thread 1 acquired Resource A")
        with resource_b:
            print("Thread 1 acquired Resource B")

def thread2():
    with resource_b:
        print("Thread 2 acquired Resource B")
        with resource_a:
            print("Thread 2 acquired Resource A")

# Create threads
t1 = threading.Thread(target=thread1)
t2 = threading.Thread(target=thread2)

# Start threads
t1.start()
t2.start()

t1.join()
t2.join()
```

In this example, if `thread1` locks `resource_a` while `thread2` locks `resource_b`, both threads will wait indefinitely for the other to release their resources, resulting in a deadlock. To prevent this, you can impose a strict order on resource acquisition.