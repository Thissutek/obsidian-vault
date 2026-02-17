2026-02-17 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Data Structures]]

# Bloom Filters

## What is it?
A Bloom filter is a space-efficient probabilistic data structure that helps determine whether an element is a member of a set. It uses multiple hash functions to map elements to a bit array, allowing for quick membership testing. However, it can return false positives, meaning it might indicate an element is in the set when it isn't, but it never gives false negatives.

## Why does it matter?
Bloom filters are important in scenarios where memory efficiency and speed are crucial, such as in databases, network systems, and large-scale applications. They can significantly reduce the amount of storage needed for membership queries, speeding up processes like searching and deduplication while maintaining a manageable level of inaccuracy.

## Example
Here's a simple example in Python that demonstrates how a Bloom filter might be implemented:

```python
class BloomFilter:
    def __init__(self, size):
        self.size = size
        self.bit_array = [0] * size
        self.hash_functions = [hash, lambda x: hash(x) * 31]

    def add(self, item):
        for func in self.hash_functions:
            index = func(item) % self.size
            self.bit_array[index] = 1

    def contains(self, item):
        return all(self.bit_array[func(item) % self.size] for func in self.hash_functions)

# Example usage
bloom = BloomFilter(10)
bloom.add("apple")
print(bloom.contains("apple"))  # True
print(bloom.contains("banana")) # False (might be false positive)
```

In this example, we create a simple Bloom filter that uses two hash functions to manage membership testing.