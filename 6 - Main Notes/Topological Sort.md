2026-03-14 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Algorithms]]

# Topological Sort

## What is it?
Topological Sort is an algorithm used to order the vertices of a directed acyclic graph (DAG) in a linear sequence. In this sequence, for every directed edge from vertex A to vertex B, A appears before B. This is particularly useful for scheduling tasks where certain tasks must be completed before others can begin.

## Why does it matter?
Topological Sort is crucial in various applications, such as task scheduling, course prerequisite resolution, and project management. In software engineering, it helps in scenarios where dependencies exist, ensuring that processes are executed in the correct order, thereby preventing errors and inefficiencies.

## Example
Imagine you have three tasks: A (submit assignment), B (study for exam), and C (take exam). Here, task A must be completed before task C, and task B must also be finished before task C. The topological sort would yield a valid order like A, B, C.

Here's a simple Python code snippet that demonstrates a topological sort using Kahn's algorithm:

```python
from collections import deque, defaultdict

def topological_sort(graph):
    in_degree = {u: 0 for u in graph}  # Initialize in-degrees
    for u in graph:
        for v in graph[u]:
            in_degree[v] += 1

    queue = deque([u for u in in_degree if in_degree[u] == 0])  # Start with nodes with no dependencies
    sorted_order = []

    while queue:
        u = queue.popleft()
        sorted_order.append(u)
        for v in graph[u]:
            in_degree[v] -= 1
            if in_degree[v] == 0:
                queue.append(v)

    return sorted_order

# Example graph of tasks
graph = {'A': ['C'], 'B': ['C'], 'C': []}
print(topological_sort(graph))  # Output: ['A', 'B', 'C'] (or any other valid order)
```