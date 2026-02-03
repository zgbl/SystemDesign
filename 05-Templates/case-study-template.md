# Case Study Template: [Problem Name]

## 1. Problem Statement
- **Goal**: [e.g., Design a URL Shortening service like TinyURL]
- **Users**: [e.g., 100M daily active users]
- **Key Features**:
  - [Feature 1]
  - [Feature 2]

## 2. Requirements & Constraints
### Functional Requirements
- [x] Requirement A
- [x] Requirement B

### Non-Functional Requirements
- [ ] Scalability (Handle X requests/sec)
- [ ] Availability (High availability vs Consistency)
- [ ] Latency (Sub-100ms response)

### Capacity Estimation (Back-of-the-envelope)
- **Traffic**: [Calculation]
- **Storage**: [Calculation]
- **Bandwidth**: [Calculation]

## 3. High-Level Design
```mermaid
graph TD
    User --> LB[Load Balancer]
    LB --> API[API Server]
    API --> DB[(Database)]
    API --> Cache[Redis Cache]
```

## 4. Component Deep Dive
### [Component A: e.g. Database Schema]
- Choice of DB: [SQL vs NoSQL]
- Schema details:

### [Component B: e.g. Key Generation]
- Algorithm:
- Pros/Cons:

## 5. Scaling & Bottlenecks
- How to handle [X bottleneck]?
- Monitoring and Metrics.

## 6. Summary / Trade-offs
- [Trade-off 1]
- [Trade-off 2]
