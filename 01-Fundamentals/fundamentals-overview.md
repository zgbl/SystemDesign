# System Design Fundamentals

This section covers the core concepts that form the backbone of any distributed system.

## 1. Scalability: Vertical vs Horizontal
Scale is the most fundamental requirement in "Big Tech" interviews.

- **Vertical Scaling (Scaling Up)**: Adding more power (CPU, RAM) to an existing server.
  - *Pros*: Simple, no change in app logic.
  - *Cons*: Hard limit (hardware max), single point of failure (SPOF).
- **Horizontal Scaling (Scaling Out)**: Adding more servers to the pool.
  - *Pros*: Theoretically infinite, high availability.
  - *Cons*: Requires Load Balancer, complexity in state management.

## 2. CAP Theorem
In a distributed system, you can only pick **two** out of three:

- **Consistency (C)**: Every read receives the most recent write or an error.
- **Availability (A)**: Every request receives a (non-error) response, without the guarantee that it contains the most recent write.
- **Partition Tolerance (P)**: The system continues to operate despite an arbitrary number of messages being dropped by the network between nodes.

> [!IMPORTANT]
> Since network partitions are inevitable in distributed systems, we usually choose between **CP** (Consistency + Partition Tolerance) and **AP** (Availability + Partition Tolerance).

## 3. Consistency Models
- **Strong Consistency**: After a write, any subsequent access will return the updated value.
- **Eventual Consistency**: If no new updates are made to a data item, eventually all accesses will return the last updated value (Common in Meta/Tiktok feeds).
- **Causal Consistency**: Ensures that operations that are causally related are seen by all processes in the same order.

## 4. Availability vs Reliability
- **Availability**: Percentage of time the system is operational (e.g., 99.99% "four nines").
- **Reliability**: Probability that the system will perform its function without failure for a specified period of time.
