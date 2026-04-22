2026-04-22 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Concurrency]]

# Concurrency vs Parallelism

## What is it?
Concurrency and parallelism are concepts related to executing multiple tasks in computing. Concurrency refers to the ability of a system to handle multiple tasks at once by managing them in a way that they appear to be progressing simultaneously, even if they are not. Parallelism, on the other hand, involves performing multiple tasks at the same exact time, typically by using multiple processors or cores.

## Why does it matter?
Understanding the difference between concurrency and parallelism is crucial for optimizing performance in software applications. While concurrency allows for better resource utilization and responsiveness (such as in web servers managing multiple requests), parallelism can significantly speed up processing by dividing tasks across multiple CPU cores. Effective use of both can lead to more efficient and responsive applications.

## Example
Here's a simple example in Python that illustrates the difference:

```python
import time
import threading

def task(name):
    print(f"{name} starting")
    time.sleep(2)
    print(f"{name} completed")

# Concurrency: Using threading to manage tasks
thread1 = threading.Thread(target=task, args=("Task 1",))
thread2 = threading.Thread(target=task, args=("Task 2",))

thread1.start()
thread2.start()

thread1.join()
thread2.join()
```

In this example, two tasks are managed concurrently using threads. They run "simultaneously" in that they can start and complete independently, but they still share the same CPU core. If you had multiple cores, you could achieve parallelism by executing them on different cores.