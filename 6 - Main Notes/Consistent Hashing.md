2026-05-27 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Algorithms]]

# Consistent Hashing

## What is it?
Consistent hashing is a technique used in distributed systems to efficiently distribute data across multiple nodes or servers. Unlike traditional hashing methods, which can require reassigning a lot of data when nodes are added or removed, consistent hashing minimizes the amount of data that needs to be moved, ensuring that most data remains in the same location.

## Why does it matter?
In real software engineering, especially in systems like databases or caching, the ability to add or remove servers without significant data shuffling is crucial for maintaining performance and reliability. Consistent hashing helps achieve scalability and fault tolerance, making it easier to manage large-scale applications that require dynamic resource allocation.

## Example
Imagine you have a pizza restaurant with multiple locations. If you assign customers to locations based on their proximity (like hashing), when a new location opens, you might have to reassign half of your customers to different locations. However, using consistent hashing, only a few customers will need to switch their pizza place, keeping most of them happy with their current location. 

Here's a simple Python example illustrating consistent hashing with a basic mapping:

```python
import hashlib

def hash_key(key, num_nodes):
    return int(hashlib.md5(key.encode()).hexdigest(), 16) % num_nodes

nodes = ['A', 'B', 'C']
key = 'customer123'
node_index = hash_key(key, len(nodes))
print(f"Key '{key}' is assigned to node '{nodes[node_index]}'")
```

This code assigns a customer to one of the nodes (A, B, or C) based on the hashed value of their identifier. When you add or remove nodes, only a small number of keys would need to be reassigned.