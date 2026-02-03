# API Design Overview

API Design is more than just defining endpoints; it's about creating a contract between services that is stable, performant, and secure. In a system design interview, you are expected to move beyond "I'll use REST" to explaining *why* a specific protocol or pattern fits the constraints.

## 1. The API Lifecycle & Philosophy

### Design-First vs. Code-First
- **Design-First**: You define the API contract (e.g., OpenAPI/Swagger) before writing code. This allows parallel development of frontend/backend and early feedback.
- **Code-First**: You implement the logic and generate the API documentation from the code. Faster for small projects but harder to maintain consistency in large systems.

### Statelessness
Modern APIs are almost always stateless. Each request must contain all the information needed to process it. This is crucial for **Horizontal Scalability**.

---

## 2. Core Constraints of Good API Design

1. **Stability**: APIs should be backward compatible. Avoid breaking changes.
2. **Performance**: Minimize payload size and round-trips.
3. **Discoverability**: Can a developer figure out how to use the API without 100 pages of docs?
4. **Security**: Proper AuthN/AuthZ at every entry point.

---

## 3. Interview Focus Areas

When asked about API design in an interview, be prepared to discuss:
- **Resource Identification**: How do you model your data?
- **Protocol Choice**: REST vs. GraphQL vs. gRPC (Trade-offs).
- **Versioning**: How do you evolve the API?
- **Pagination**: How do you handle large datasets?
- **Error Handling**: Standardized vs. Custom error structures.
- **Rate Limiting & Throttling**: How do you protect the system from "noisy neighbors"?

---

## 4. Next Steps
- [**REST API Deep Dive**](./01-rest-api.md)
- [**GraphQL Deep Dive**](./02-graphql.md)
- [**gRPC & RPC Deep Dive**](./03-grpc-rpc.md)
- [**Advanced Patterns (Idempotency, Security, Webhooks)**](./04-advanced-patterns.md)
