2026-06-19 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# CAP Theorem

## What is it?
The CAP Theorem, also known as Brewer's theorem, states that in a distributed data store, you can only guarantee two out of the following three properties at the same time: Consistency, Availability, and Partition Tolerance. Consistency means that all nodes see the same data at the same time. Availability ensures that every request receives a response, whether successful or failed. Partition Tolerance means the system continues to operate despite network failures.

## Why does it matter?
Understanding the CAP Theorem is crucial for software engineers designing distributed systems, such as cloud applications. It helps them make informed decisions about trade-offs when designing systems that need to handle large amounts of data and user requests. For instance, prioritizing consistency might lead to downtime during network issues, while focusing on availability might risk serving outdated data.

## Example
Consider a simple online banking system where users retrieve their account balances. If two users try to check their balance simultaneously, and one user makes a withdrawal, the system must decide whether to allow both users to see the same balance (consistency) or to ensure that both can access the service even if it means they might see outdated balances (availability). If there’s a network split, the system could either refuse access to one user to maintain consistency or allow both users to access it for availability, but it can’t ensure both at the same time.