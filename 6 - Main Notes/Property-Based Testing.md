2026-03-10 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Testing & Practices]]

# Property-Based Testing

## What is it?
Property-based testing is a testing methodology where instead of writing specific input-output pairs to test your code, you define general properties that should hold true for a wide range of inputs. For example, if you have a function that sorts an array, a property might be that the output array is always sorted, regardless of the input array.

## Why does it matter?
Property-based testing is important because it helps uncover edge cases and unexpected behaviors that traditional example-based testing might miss. It encourages developers to think about the contract of their functions and ensures that the code behaves correctly across many scenarios, ultimately leading to more robust and reliable software.

## Example
Here's a simple example in Python using the `hypothesis` library for property-based testing:

```python
from hypothesis import given
import hypothesis.strategies as st

def sort_array(arr):
    return sorted(arr)

@given(st.lists(st.integers()))
def test_sorted_property(arr):
    sorted_arr = sort_array(arr)
    assert sorted_arr == sorted(sorted_arr)  # Output should be sorted

# This test will run with many different lists of integers
```

In this example, the `@given` decorator generates various lists of integers to check if the `sort_array` function consistently returns a sorted list.