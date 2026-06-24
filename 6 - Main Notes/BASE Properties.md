2026-06-24 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# BASE Properties

## What is it?
BASE is an acronym that stands for Basically Available, Soft state, and Eventually consistent. It’s a set of properties used primarily in distributed systems and databases, emphasizing flexibility and availability over strict consistency. Unlike the traditional ACID properties, which ensure strong consistency, BASE allows systems to function effectively even when some nodes may be temporarily unavailable.

## Why does it matter?
In real-world software engineering, particularly in large-scale applications and cloud environments, systems often handle massive amounts of data across distributed locations. BASE properties enable developers to build applications that remain operational and responsive, even during failures. This is crucial for user experience, as users expect applications to be available at all times, even if that means some data might be outdated temporarily.

## Example
Imagine a social media app where you can post updates and see what friends are sharing. When you post an update, it might not immediately reflect on all friends' feeds due to network latency. While some friends may see your old status for a short time (soft state), eventually, everyone will see your latest update (eventually consistent). This design prioritizes the app being always available over ensuring that everyone sees the same information at the exact same moment. Here's a simplified representation in Python:

```python
class SocialMediaApp:
    def __init__(self):
        self.feed = []

    def post_update(self, update):
        self.feed.append(update)  # Basically available
        # Simulate asynchronous updates
        print("Your update is posted!")

    def view_feed(self):
        return self.feed  # Soft state, may not be up-to-date for everyone

app = SocialMediaApp()
app.post_update("Hello, world!")
print(app.view_feed())
```