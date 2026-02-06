2025-12-03 12:00

Status:
Tag: [[database]] [[data structure]]

# Neo4j

## What is it?

Neo4j is a **graph database** — a NoSQL database that stores data as nodes, relationships, and properties rather than traditional tables. Think of it like a whiteboard where you draw circles (nodes) and connect them with arrows (relationships).

Unlike relational databases like [[SQL]] that use tables and require JOINs to connect data, Neo4j stores relationships natively alongside the data. This makes traversing connections extremely fast — millions of relationships per second.

### Core Components

**Nodes** — Entities or objects (e.g., Person, Product, Company)
- Can have zero or more **labels** to classify them
- Hold **properties** as key-value pairs

**Relationships** — Named connections between nodes
- Always have a direction (start → end)
- Must have exactly one type (e.g., FOLLOWS, PURCHASED, KNOWS)
- Can also hold properties

**Properties** — Key-value data attached to nodes or relationships

```
(:Person {name: "Alice"})-[:KNOWS {since: 2020}]->(:Person {name: "Bob"})
```

## Why does it matter?

### When to Use Graph Databases

1. **Highly connected data** — Social networks, recommendation engines, fraud detection
2. **Relationship-heavy queries** — "Find friends of friends who like X"
3. **Real-time traversals** — Following paths through data without expensive JOINs
4. **Flexible schemas** — Data models that evolve over time

### Neo4j vs Relational Databases

| Aspect | Neo4j | Relational (SQL) |
|--------|-------|------------------|
| Data model | Nodes + Relationships | Tables + Rows |
| Connections | Stored natively | Calculated via JOINs |
| Schema | Flexible/optional | Fixed |
| Query language | Cypher | SQL |
| Best for | Connected data | Structured records |

### Key Benefits

- **Performance** — Index-free adjacency means no costly JOINs
- **ACID compliant** — Full transaction support
- **Intuitive modeling** — Data looks like a whiteboard sketch
- **Cypher query language** — SQL-like but optimized for graphs

### Common Use Cases

- **Social networks** — Friend recommendations, influence mapping
- **Fraud detection** — Identifying suspicious patterns in transactions
- **Recommendation engines** — "Users who bought X also bought Y"
- **Knowledge graphs** — Connecting concepts for AI/LLM applications (see [[LangChain]])
- **Supply chain** — Tracking product origins and dependencies
- **Network/IT operations** — Mapping infrastructure dependencies

## Example

### Cypher Query Language

Creating nodes and relationships:
```cypher
// Create people
CREATE (alice:Person {name: 'Alice', age: 30})
CREATE (bob:Person {name: 'Bob', age: 25})

// Create relationship
CREATE (alice)-[:KNOWS {since: 2020}]->(bob)
```

Querying connected data:
```cypher
// Find all people Alice knows
MATCH (alice:Person {name: 'Alice'})-[:KNOWS]->(friend)
RETURN friend.name

// Find friends of friends
MATCH (alice:Person {name: 'Alice'})-[:KNOWS*2]->(fof)
RETURN DISTINCT fof.name
```

### Deployment Options

- **Neo4j Aura** — Fully managed cloud (AWS, GCP, Azure)
- **Neo4j Desktop** — Local development
- **Docker** — Containerized deployment (see [[What is Docker]])
- **Kubernetes** — Orchestrated clusters (see [[What is Kubernetes]])

## Graph Database Concepts

### Traversal
Visiting nodes by following relationships. Unlike SQL JOINs which recalculate connections, graph traversal follows pre-stored paths.

### Path
A sequence of nodes connected by relationships. Path length = number of relationships.

### Labels
Tags that classify nodes into groups (e.g., `:Person`, `:Product`). A node can have multiple labels.

## Comparison with Other Graph Databases

Neo4j is a **native** graph database (stores graphs at the storage level). Others include:
- **Amazon Neptune** — AWS managed graph database
- **Azure CosmosDB** — Multi-model with graph support
- **OrientDB** — Multi-model graph database
- **ArangoDB** — Multi-model with graph features

## References

- [Neo4j Documentation](https://neo4j.com/docs/)
- [Cypher Query Language](https://neo4j.com/developer/cypher/)
- [Neo4j on AWS](https://aws.amazon.com/blogs/apn/when-to-use-a-graph-database-like-neo4j-on-aws/)
