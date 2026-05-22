2026-05-22 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[Testing & Practices]]

# Technical Debt Management

## What is it?
Technical debt refers to the concept of taking shortcuts in software development that may save time in the short term but lead to more complex and costly issues later on. Just like financial debt, if you don't address it, it can accumulate interest, making it harder to manage in the future. Managing technical debt involves identifying, prioritizing, and making plans to address these shortcuts to ensure long-term project health.

## Why does it matter?
In real software engineering, neglecting technical debt can lead to decreased productivity, increased bugs, and higher maintenance costs. By actively managing it, teams can maintain cleaner codebases, improve system performance, and ensure smoother future development. Ultimately, it helps in delivering better software faster while also making it easier to adapt to changing requirements.

## Example
Imagine you're building a house and decide to use cheaper materials for the walls to save money and time. Initially, everything looks fine, but over time, the walls start to crack and need repairs, costing more than if you'd just used quality materials from the start. 

In code:

```python
def calculate_discount(price, discount):
    # TODO: Handle cases where discount > price
    return price - (price * discount)

# Short-term solution that needs revisiting
```

Here, the code works for now, but ignoring the future case of a discount greater than the price creates technical debt that could lead to issues later.