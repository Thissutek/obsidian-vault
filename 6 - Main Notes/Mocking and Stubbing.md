2026-02-26 01:03

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Testing & Practices]]

# Mocking and Stubbing

## What is it?
Mocking and stubbing are techniques used in software testing to simulate the behavior of complex, real-world objects. Stubs provide predefined responses to specific calls made during a test, while mocks are more advanced and can verify interactions, such as how many times a method was called and with what parameters.

## Why does it matter?
These techniques are crucial because they allow developers to isolate the unit of code being tested without relying on the actual implementation of dependencies, such as databases or APIs. This isolation makes tests faster, more reliable, and easier to write, ensuring that code behaves correctly in various scenarios without the overhead of real interactions.

## Example
Here’s a simple example in Python using the `unittest` library with mocking:

```python
import unittest
from unittest.mock import Mock

def fetch_data(api):
    return api.get_data()

class TestFetchData(unittest.TestCase):
    def test_fetch_data(self):
        mock_api = Mock()
        mock_api.get_data.return_value = {'key': 'value'}

        result = fetch_data(mock_api)
        self.assertEqual(result, {'key': 'value'})
        mock_api.get_data.assert_called_once()

if __name__ == '__main__':
    unittest.main()
```

In this example, `mock_api` serves as a mock object that simulates an API without making actual network calls. The test verifies that `fetch_data` correctly interacts with this mock by calling `get_data`.