## Distributed Systems

### Concepts

#### Fallacies of Distributed Computing
1. The network is reliable  
2. Latency is zero  
3. Bandwidth is infinite  
4. The network is secure  
5. Topology doesn’t change  
6. There is one administrator  
7. Transport cost is zero  
8. The network is homogeneous  

_These are incorrect assumptions that often lead to flawed distributed system designs._

---

#### Synchronous vs. Asynchronous
- **Synchronous**: Sender waits for a response before continuing (tight coupling, predictable order, but higher latency risk).  
- **Asynchronous**: Sender doesn’t wait for a response (looser coupling, higher throughput, but harder to debug and reason about).  

---

#### Event Log vs. Message Queue
- **Event Log**: Persistent, append-only store of events (e.g., Kafka). Consumers can replay events.  
- **Message Queue**: Typically FIFO delivery, messages are consumed once and removed (e.g., RabbitMQ).  

---

#### Exactly-Once Delivery
- Achieving true "exactly-once" delivery in distributed systems is extremely hard.  
- Usually implemented via **idempotent operations** and **at-least-once delivery** with deduplication.  

---

#### Different Types of Message Failure
- **Lost messages** (dropped before reaching recipient)  
- **Duplicate messages** (due to retries)  
- **Out-of-order messages** (network reordering)  
- **Corrupted messages** (rare, but possible)  

---

#### Orchestration vs. Choreography
- **Orchestration**: Central controller dictates interactions (workflow engines).  
- **Choreography**: Each service reacts to events and coordinates indirectly (event-driven).  

---

#### Causality
- Determines whether one event happened before another.  
- Often tracked with **Lamport timestamps** or **vector clocks**.  

---

#### CDN (Content Delivery Network)
- Distributed cache of static or semi-static assets close to users.  
- Reduces latency and server load.  

---

### Hashing

#### Consistent Hashing
- Distributes keys across nodes in a way that minimizes remapping when nodes join/leave.  
- Used in caching, sharding, and load balancing.  

#### Geohashing
- Encodes geographic coordinates into a short string or number.  
- Useful for location-based lookups.  

#### Perfect Hashing
- A hashing function with no collisions for a given dataset.  
- Typically used for static datasets.  

---

### Read-Heavy vs. Write-Heavy Impacts
- **Read-heavy**: Focus on caching, replication, and query optimization.  
- **Write-heavy**: Optimize for partitioning, batch writes, and efficient consensus.  

---

### Federation
- Independent systems (or clusters) that work together via standardized protocols.  
- Example: Multiple Kubernetes clusters federated for global deployments.  

---

### Latency

#### Latency, Throughput, Goodput
- **Latency**: Time taken for a single request/response.  
- **Throughput**: Requests processed per unit time.  
- **Goodput**: Throughput of *useful* data (excludes retransmissions, headers, etc.).  

#### Latency Numbers Every Programmer Should Know
- Accessing L1 cache: ~0.5ns  
- Accessing main memory: ~100ns  
- Disk seek: ~10ms  
- Cross-country network: ~70ms  

#### How to Prevent Latency Variability
- Avoid garbage collection pauses  
- Use predictable scheduling  
- Control network jitter  

#### Tail Latency
- The latency experienced by the slowest percentile of requests (e.g., 99th percentile).  
- Can dominate user experience in large-scale systems.  

---

### How to Reduce Sharing
- Reduce contention on shared resources.  
- Prefer partitioning data so that each node works independently.  

---

### Idempotency
- Operation that can be applied multiple times without changing the result after the first application.  
- Critical for retries in distributed systems.  

---

### Load Balancer

#### Concepts
- Distributes incoming traffic across multiple servers to improve reliability and performance.  

#### Layer 4 vs. Layer 7 Load Balancer
- **Layer 4**: Operates at TCP/UDP level, routing based on IP and port.  
- **Layer 7**: Operates at HTTP/HTTPS level, routing based on URL, headers, or content.  

---

### Liveness vs. Safety Properties
- **Liveness**: Something good eventually happens (progress).  
- **Safety**: Nothing bad ever happens (correctness).  

---

### Microservices: Pros and Cons
- **Pros**: Scalability, flexibility in tech stack, independent deployments.  
- **Cons**: Operational complexity, network latency, data consistency challenges.  

---

### REST
- Resource-based communication using HTTP verbs (GET, POST, PUT, DELETE).  
- Stateless, cache-friendly.  

---

### gRPC
- High-performance, contract-first RPC framework using Protocol Buffers.  
- Supports streaming and bidirectional communication.  

---

### Service Mesh
- Infrastructure layer for service-to-service communication.  
- Handles routing, observability, retries, and security. Example: Istio, Linkerd.  

---

### Source of Truth
- The authoritative dataset or system from which all other copies are derived.  

---

### Stateful vs. Stateless
- **Stateful**: Retains session/data between requests (e.g., databases).  
- **Stateless**: Treats each request independently (e.g., REST API).  

---

### Total vs. Partial Order
- **Total Order**: Every pair of elements is comparable.  
- **Partial Order**: Some elements may be incomparable (e.g., concurrent events).  

---

### Why Can't We Rely on the System Clock in Distributed Systems
- Clock drift between machines  
- Network latency affecting synchronization  
- Instead, use logical clocks (Lamport, vector clocks).  

---

### Vector Clock
- Tracks causal relationships between events in distributed systems.  
- Each process maintains a vector of counters for all processes.  
