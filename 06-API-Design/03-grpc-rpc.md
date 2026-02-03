# gRPC & RPC Deep Dive

RPC (Remote Procedure Call) allows a program to cause a procedure to execute in another address space as if it were a local call. gRPC is a modern implementation of RPC by Google.

## 1. Protocol Buffers (Protobuf)
- **Concept**: Language-neutral, platform-neutral, extensible mechanism for serializing structured data.
- **Advantages over JSON**:
  - **Size**: Binary format is much smaller.
  - **Speed**: Faster serialization/deserialization.
  - **Type Safety**: Strictly typed schema (`.proto` files).
  - **Backward Compatibility**: Fields can be added without breaking old clients.

## 2. HTTP/2 as the Transport
gRPC uses HTTP/2, which provides:
- **Multiplexing**: Many requests over a single TCP connection.
- **Header Compression (HPACK)**: Reduces overhead.
- **Server Push**: Server can push data to client.
- **Binary Framing**: More efficient than text-based HTTP/1.1.

## 3. gRPC Streaming Types
1. **Unary**: Simple Request -> Response.
2. **Server Streaming**: Request -> Stream of Responses (e.g., Live ticker).
3. **Client Streaming**: Stream of Requests -> Response (e.g., Uploading large files).
4. **Bi-directional Streaming**: Stream of Requests <-> Stream of Responses (e.g., Chat apps).

## 4. Why gRPC for Microservices?
- **Efficiency**: Low latency and high throughput.
- **Polyglot**: Work with different languages easily via generated stubs.
- **Strict Contract**: The `.proto` file is the ultimate source of truth.
- **Interceptors**: Middleware for logging, auth, and monitoring.

## 5. Trade-offs & Limitations
- **Browser Support**: Browsers cannot directly speak gRPC (requires `grpc-web` proxy).
- **Human Readability**: You can't just `curl` a gRPC endpoint and read the text.
- **LB Complexity**: Layer 7 Load Balancing is harder with long-lived HTTP/2 connections.

---

## Next Steps
- [**Advanced Patterns**](./04-advanced-patterns.md)
- [**API Design Overview**](./api-design-overview.md)
