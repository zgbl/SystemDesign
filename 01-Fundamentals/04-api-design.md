# API Design Fundamentals

API design is a critical part of system design. A well-designed API is intuitive, scalable, and easy to maintain.

## 1. API Protocols

### REST (Representational State Transfer)
- **Concept**: Resource-based, uses standard HTTP methods (GET, POST, PUT, DELETE).
- **Pros**: Simple, widely adopted, cacheable.
- **Cons**: Over-fetching or under-fetching of data.

### GraphQL
- **Concept**: Query language for your API, clients request exactly what they need.
- **Pros**: No over-fetching, strongly typed schema.
- **Cons**: Complex to implement, difficult to cache.

### gRPC (Google Remote Procedure Call)
- **Concept**: High-performance, uses Protocol Buffers (Protobuf) and HTTP/2.
- **Pros**: Fast, compact, strictly typed, supports streaming.
- **Cons**: Harder for browser clients to use directly, less human-readable.

---

## 2. API Versioning

- **URI Versioning**: `/v1/users/123` (Most common).
- **Query Parameter**: `/users/123?version=1`.
- **Header Versioning**: `Accept: application/vnd.myapi.v1+json`.

---

## 3. Error Handling & Status Codes

| Code | Meaning | Usage |
|------|---------|-------|
| 200 | OK | Success |
| 201 | Created | Successful resource creation |
| 400 | Bad Request | Client-side input error |
| 401 | Unauthorized | Authentication required |
| 403 | Forbidden | Authenticated but no permission |
| 404 | Not Found | Resource does not exist |
| 429 | Too Many Requests | Rate limited |
| 500 | Internal Server Error | Server-side crash/error |

---

## 4. Advanced Concepts

### Idempotency
An idempotent API is one where multiple identical requests have the same effect as a single request.
- **Usage**: Use `Idempotency-Key` headers for POST requests to prevent double-billing or duplicate creation.

### Rate Limiting
Protect your services from abuse.
- **Algorithms**: Token Bucket, Leaky Bucket, Fixed Window, Sliding Window Logger.

### Pagination
- **Offset-based**: `OFFSET 10 LIMIT 10`. Simple but slow for large datasets.
- **Cursor-based**: `after_id=XYZ`. More performant and handles real-time data better.
