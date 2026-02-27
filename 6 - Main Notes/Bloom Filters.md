2026-02-26 21:14

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Data Structures]]

# Bloom Filters

## What is it?
A Bloom Filter is a space-efficient probabilistic data structure used to test whether an element is a member of a set. It allows for fast membership checks with the trade-off that it may sometimes falsely indicate that an element is present (a false positive), but it will never falsely indicate that an element is absent (no false negatives).

## Why does it matter?
Bloom Filters are important in software engineering because they help reduce memory usage and improve performance in applications that require fast membership checks, such as caching, databases, and network applications. They are especially useful when dealing with large datasets where traditional data structures would consume too much memory or when we want to minimize disk I/O operations.

## Example
Here's a simple example in Python to illustrate a Bloom Filter using a list of bits and multiple hash functions:

```python
class BloomFilter:
    def __init__(self, size, hash_functions):
        self.size = size
        self.bit_array = [0] * size
        self.hash_functions = hash_functions

    def add(self, item):
        for func in self.hash_functions:
            index = func(item) % self.size
            self.bit_array[index] = 1

    def contains(self, item):
        return all(self.bit_array[func(item) % self.size] for func in self.hash_functions)

# Example usage
hash_funcs = [hash, lambda x: hash(x) * 2]  # Simple hash functions
bloom = BloomFilter(10, hash_funcs)
bloom.add("apple")
print(bloom.contains("apple"))  # True
print(bloom.contains("banana"))  # May return False (or True due to false positive)
```

In this example, we create a Bloom Filter with a bit array and two simple hash functions to add and check for items efficiently.