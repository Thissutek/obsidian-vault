2026-03-20 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Testing & Practices]]

# Mocking and Stubbing

## What is it?
Mocking and stubbing are techniques used in software testing to replace real objects with controlled replacements. A **stub** is a minimal implementation of an object that returns predetermined responses for specific calls, while a **mock** is a more complex object that can verify interactions, such as whether a method was called or not.

## Why does it matter?
These techniques are crucial for isolating the unit of code being tested, which allows developers to focus on the function's logic without being affected by external systems like databases or APIs. By using mocks and stubs, developers can simulate various scenarios and edge cases, leading to more thorough testing and higher code quality.

## Example
Here’s a simple example in Python using the `unittest` library:

```python
from unittest import TestCase
from unittest.mock import Mock

# Function to test
def get_user_data(api):
    return api.fetch_user()

class TestUserData(TestCase):
    def test_get_user_data(self):
        # Create a mock object for the API
        mock_api = Mock()
        mock_api.fetch_user.return_value = {'name': 'Alice'}

        # Call the function with the mock
        result = get_user_data(mock_api)

        # Verify the result and that the method was called
        self.assertEqual(result, {'name': 'Alice'})
        mock_api.fetch_user.assert_called_once()
```

In this example, we stub the `fetch_user` method to return a specific value, and we also use a mock to check if it was called exactly once during the test.