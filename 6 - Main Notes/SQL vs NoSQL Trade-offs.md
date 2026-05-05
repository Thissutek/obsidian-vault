2026-05-05 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# SQL vs NoSQL Trade-offs

## What is it?
SQL (Structured Query Language) databases are relational databases that store data in structured tables with predefined schemas, using a structured format like rows and columns. NoSQL (Not Only SQL) databases, on the other hand, are non-relational and can store unstructured or semi-structured data, allowing for more flexibility in data models.

## Why does it matter?
Understanding the trade-offs between SQL and NoSQL databases is crucial for software engineers because it directly impacts application performance, scalability, and the ability to handle diverse data types. SQL databases are typically better for complex queries and transactions, while NoSQL databases excel in handling large volumes of varied data across distributed systems.

## Example
Imagine you have a library system. If you use an SQL database, you might structure it like this:

```sql
CREATE TABLE Books (
    ID INT PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    PublishedYear INT
);
```

This table enforces strict rules about what data you can enter. In contrast, using a NoSQL database (like MongoDB), you could store book data more flexibly without a rigid structure:

```json
{
    "Title": "The Great Gatsby",
    "Author": "F. Scott Fitzgerald",
    "PublishedYear": 1925,
    "Genres": ["Fiction", "Classic"]
}
```

Here, you could easily add new fields, like "Genres," without altering the overall structure, making it easier to adapt as your needs evolve.