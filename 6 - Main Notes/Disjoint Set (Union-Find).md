2026-03-16 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Data Structures]]

# Disjoint Set (Union-Find)

## What is it?
A Disjoint Set, also known as Union-Find, is a data structure that keeps track of a collection of non-overlapping sets. It provides two main operations: **union**, which merges two sets, and **find**, which identifies the set a particular element belongs to. This is useful for managing dynamic connectivity between elements, like tracking group memberships.

## Why does it matter?
Disjoint Sets are crucial in solving problems related to connectivity and clustering, such as network connectivity, image processing, and Kruskal's algorithm for finding the minimum spanning tree in graphs. They efficiently manage and reduce complexity when dealing with dynamic groupings, making them essential for optimizing algorithms in software engineering.

## Example
Here’s a simple implementation in Python that demonstrates union and find operations:

```python
class DisjointSet:
    def __init__(self):
        self.parent = {}

    def find(self, item):
        if self.parent[item] != item:
            self.parent[item] = self.find(self.parent[item])  # Path compression
        return self.parent.setdefault(item, item)

    def union(self, set1, set2):
        root1 = self.find(set1)
        root2 = self.find(set2)
        if root1 != root2:
            self.parent[root2] = root1  # Merge sets

# Example usage:
ds = DisjointSet()
ds.union('A', 'B')
print(ds.find('B'))  # Output: 'A'
```

In this code, we create a `DisjointSet` class that can unite elements and find their root representatives, demonstrating the core functionality of the data structure.