# Databases & Storage

Choosing the right storage is critical in Google/Meta interviews.

## 1. SQL vs NoSQL

| Feature | SQL (Relational) | NoSQL (Non-Relational) |
| :--- | :--- | :--- |
| **Schema** | Fixed, predefined | Dynamic, flexible |
| **Scaling** | Vertical (mostly) | Horizontal (sharding) |
| **Consistency** | ACID | BASE (Eventual) |
| **Use Case** | Financial, transaction data | Big data, real-time social feeds |

## 2. NoSQL Types
- **Key-Value**: (Redis, DynamoDB) - Ultra fast, simple lookups.
- **Document**: (MongoDB, CouchDB) - Flexible schema for app data.
- **Wide-Column**: (Cassandra, HBase) - High write throughput, great for time-series or logs.
- **Graph**: (Neo4j) - Relationships (e.g., Meta's Social Graph).

## 3. Sharding (Horizontal Partitioning)
Dividing a large database into smaller, faster, more easily managed parts (shards).
- **Key-based**: Hashing a key (e.g., UserID) to find the shard.
- **Range-based**: Range of values (e.g., users with names A-M).
- **Directory-based**: Keeping a lookup table.

## 4. Replication
- **Leader-Follower (Master-Slave)**: One leader for writes, multiple followers for reads.
- **Leader-Leader (Multi-Master)**: Multiple nodes handle writes (complex conflict resolution).
