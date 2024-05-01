# Module 9
> M Azmy Arya Rizaldi M - 2206081704

#### 1. Unary, server streaming, and bi-directional streaming RPC key differences:
- ##### **Unary RPC**: 
    In a unary RPC, the client sends a **single request** to the    server and receives a **single response**. This method is suitable for simple request-response interactions where the client needs a single answer from the server.
- ##### **Server streaming RPC**: 
    In server streaming RPC, the client sends a **single request** to the server and receives a **stream of responses**. This method is useful when the server needs to send multiple pieces of data in response to a single request, such as fetching a large dataset or real-time updates.
- ##### **Bi-directional streaming RPC**: 
    In bi-directional streaming RPC, **both the client and server can send a stream of messages independently**. This method is suitable for scenarios where both client and server need to send a continuous stream of data, such as chat applications or real-time collaborative editing.
        
#### 2. **Security considerations**: 
In implementing a gRPC service in Rust, ensuring security involves authentication, authorization, and data encryption. We can use authentication mechanisms like Transport Layer Secyrity (TLS) for securing communication channels, implement authorization checks at the service level to control access to resources, and use encryption techniques to protect data security.

#### 3. **Challenges with bidirectional streaming**: 
In Rust gRPC, handling bidirectional streaming can cause a scenario like chat applications where maintaining connections, handling concurrent messages, and ensuring message delivery order can be complex. We may encounter issues related to synchronization and resource management.

#### 4. **Advantages and disadvantages of using ReceiverStream**: 
The `ReceiverStream` from `tokio_stream::wrappers` provides a convenient way to convert a `tokio::sync::mpsc::Receiver` into a stream. 
- **Advantages** include ease of integration with Tokio-based asynchronous code. 
- However, it might **introduce complexity** when dealing with error handling.

#### 5. **Code structure for reuse and modularity**: 
To promote maintainability and extensibility in Rust gRPC code, you can structure it into reusable modules, separate concerns like business logic and networking, use traits and generics for abstraction, and follow the SOLID principles. This approach facilitates testing, dependency management, and future enhancements.

#### 6. **Handling complex payment processing logic**:
In a `MyPaymentService` implementation, additional steps might involve validating payment data, handling various payment methods, integrating with external payment service, and implementing error recovery mechanisms.

#### 7. **Impact of gRPC on distributed systems architecture**: 
Adopting gRPC affects the overall architecture by enabling efficient communication between distributed components using a language-neutral, high-performance protocol. It supports multiple programming languages and platforms through code generation from protocol buffers.

#### 8. **Advantages and disadvantages of HTTP/2**: 
Compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs, HTTP/2 offers advantages like multiplexing, header compression, server push, and stream prioritization, improving performance and reducing latency. However, it may introduce complexity in debugging and infrastructure setup compared to HTTP/1.1.

#### 9. **Contrast between REST APIs and gRPC**: 
The request-response model of REST APIs is suitable for traditional client-server interactions, but it lacks real-time capabilities and can be less efficient for streaming data. In contrast, gRPC's bidirectional streaming allows for efficient real-time communication, making it more responsive for applications like chat or live updates.

#### 10. **Implications of schema-based approach of gRPC**: 
- Using Protocol Buffers for schema definition in gRPC offers advantages like efficient serialization, backward and forward compatibility, and code generation for multiple languages. 
- However, it may be less flexible than JSON in REST API payloads, especially in dynamic environments where there is a lot of schema changes.