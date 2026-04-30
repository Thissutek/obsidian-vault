2026-04-30 09:00

Status:
Tag: [[Software Engineering]] [[Daily Concept]] [[System Design]]

# Write-Ahead Logging

## What is it?
Write-Ahead Logging (WAL) is a technique used in databases to ensure data integrity. It works by recording changes to a log before they are applied to the main database, which allows recovery from crashes by replaying the log to restore the last consistent state.

## Why does it matter?
WAL is crucial for maintaining the reliability of databases, especially in systems that require high availability. In the event of a failure, being able to restore data from the log means that important information isn't lost, and the database can recover to a consistent state quickly, minimizing downtime and data loss.

## Example
Imagine you’re writing a journal. Before you make changes to the actual pages (like adding an entry), you first jot down the changes on a loose sheet of paper. If you accidentally spill coffee on your journal, you can recreate the last entry by looking at your notes on the loose sheet instead of losing your thoughts entirely. 

In code, a simplified version of WAL might look like this in Python:

```python
def write_ahead_log(transaction, log_file):
    with open(log_file, 'a') as log:
        log.write(transaction + '\n')  # Log the transaction first
    apply_transaction(transaction)  # Then apply it to the database
```

Here, the transaction is first logged before being applied, ensuring that we can always replay it if anything goes wrong.