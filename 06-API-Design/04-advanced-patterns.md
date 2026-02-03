# Advanced API Patterns

This section covers cross-cutting concerns that apply across all API protocols. Mastering these is key for Senior and Staff-level system design interviews.

## 1. Idempotency
An idempotent operation is one that has no additional effect if it is called more than once with the same input parameters.
- **Why?** Distributed systems are unreliable. Network timeouts can happen after a server has processed a request but before the client receives the response.
- **Implementation**:
  - Client sends a unique `Idempotency-Key` (UUID).
  - Server checks if the key exists in a cache (e.g., Redis).
  - If it exists, return the cached response.
  - If not, process the request and store the result.

## 2. Rate Limiting & Throttling
Protecting your system from "Noisy Neighbors" and DDoS attacks.
- **Algorithms**:
  - **Token Bucket**: Allows for bursts, constant average rate.
  - **Leaky Bucket**: Smooths out bursts, constant output rate.
  - **Fixed Window**: Simple, but spikes at window boundaries.
  - **Sliding Window Log/Counter**: More accurate but higher memory/compute cost.
- **Levels**: API Key level, User level, IP level.

## 3. API Security Best Practices
- **Authentication (AuthN)**: Who are you? (OAuth2, API Keys).
- **Authorization (AuthZ)**: What can you do? (RBAC, ABAC).
- **Encryption**: Always use HTTPS (TLS).
- **Input Validation**: Never trust client data; sanitize against SQL injection, XSS, etc.
- **JWT (JSON Web Tokens)**: Stateless authentication. Use with short expiration and refresh tokens.

## 4. Real-time Communication
- **Short Polling**: Client hits server every X seconds. Efficient for server, wasteful for client.
- **Long Polling**: Server holds the request open until data is available.
- **WebSockets**: Full-duplex TCP connection. Best for low-latency bi-directional apps.
- **Server-Sent Events (SSE)**: One-way stream from server to client. Easier to implement over HTTP than WebSockets.

## 5. Pagination Deep Dive
- **Offset-based**: `page=2&size=20`. Simple, but slow for deep pages and problematic if data changes during navigation.
- **Cursor-based**: `after_id=XYZ`. Most efficient for large datasets and infinite scrolls. The "cursor" is an opaque string representing a pointer to the next set.

---

## Conclusion
A great API is predictable. Use standard protocols where possible, document everything, and design for the edge cases (failures, retries, and high scale).
