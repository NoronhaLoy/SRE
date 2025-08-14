## Databases

---

### **Different types of databases**
* **Relational Databases (SQL)**
  * Structured, table-based data with predefined schema.
  * Examples: PostgreSQL, MySQL, Oracle.
* **NoSQL Databases**
  * Flexible schemas, suited for unstructured or semi-structured data.
  * Categories: Document, Columnar, Key-Value, Graph.
* **Vector Databases**
  * Specialized for storing and querying high-dimensional vectors (e.g., embeddings for AI/ML).
  * Examples: Pinecone, Milvus.
* **Object-based Storage**
  * Data stored as objects with metadata and unique IDs.
  * Examples: Amazon S3, MinIO.

---

### **NoSQL vs. SQL**
* **SQL**
  * Structured schema.
  * Strong ACID guarantees.
  * Best for complex queries and relationships.
* **NoSQL**
  * Flexible schema, horizontal scaling.
  * Often eventual consistency.
  * Best for high throughput and distributed systems.

---

### **Relational vs. Document**
* **Relational** – Table-based, normalized data.
* **Document** – JSON/BSON-style objects, flexible schema.

---

### **Column-oriented Databases**
* Store data by columns instead of rows.
* Great for analytics and aggregations.
* Examples: Apache Cassandra, HBase.

---

### **Graph Databases**
* Store nodes (entities) and edges (relationships).
* Ideal for social networks, recommendation systems.
* Examples: Neo4j, JanusGraph.

---

### **ACID**
* **Atomicity** – Transactions are all-or-nothing.
* **Consistency** – Data remains valid after transactions.
* **Isolation** – Transactions don’t interfere with each other.
* **Durability** – Changes persist even after failures.

---

### **Partitioning**
* Splitting large datasets across multiple nodes for scalability.
* **Criteria**:
  * Range-based partitioning
  * Hash-based partitioning
  * List-based partitioning
* **Methods**:
  * Horizontal (by rows)
  * Vertical (by columns)

---

### **Replication vs. Partition**
* **Replication** – Copy same data to multiple nodes.
* **Partitioning** – Split data across nodes.

---

### **Hotspot**
* A single partition or node receives disproportionate traffic, causing performance bottlenecks.

---

### **Theorems**
* **CALM Theorem** – Consistency as Logical Monotonicity; certain computations can be eventually consistent.
* **CAP Theorem** – You can only have two of Consistency, Availability, Partition tolerance.
* **PACELC Theorem** – Extends CAP: If Partitioned → trade Consistency/Availability; Else → trade Latency/Consistency.

---

### **Cardinality**
* Measure of uniqueness in a column.
* High cardinality: Many unique values (e.g., user ID).
* Low cardinality: Few unique values (e.g., Boolean flag).

---

### **Chain Replication**
* Data replicated in a chain fashion for strong consistency.

---

### **Consensus**
* Agreement among distributed nodes.
* Algorithms: Paxos, Raft.

---

### **Concurrency Control**
* Ensures correct results when multiple transactions occur simultaneously.
* Techniques: Locking, MVCC.

---

### **Consistency Models**
* Strong Consistency – Reads always return latest write.
* Eventual Consistency – Updates propagate eventually.
* Causal Consistency – Reads respect causality order.

---

### **Isolation Levels**
* Read Uncommitted
* Read Committed
* Repeatable Read
* Serializable (Strongest)

---

### **Serializability**
* Transactions appear to run sequentially.

---

### **Linearizability**
* Strongest consistency; operations appear instantaneously.

---

### **CRDT (Conflict-free Replicated Data Types)**
* Data structures that converge without coordination.

---

### **Indexes**
* **Primary Index** – Based on primary key, unique.
* **Secondary Index** – Built on non-primary attributes.
* **Tradeoffs** – Faster reads but slower writes & more storage.

---

### **Denormalization**
* Adding redundancy to reduce joins and improve read performance.

---

### **View vs. Materialized View**
* **View** – Virtual table generated dynamically from a query.
* **Materialized View** – Stored result of a query, periodically refreshed.

---

### **Transaction**
* Unit of work executed atomically.

---

### **Distributed Transactions Downsides**
* Higher latency.
* Increased complexity.
* Risk of deadlocks.

---

### **Strategies to Handle Rebalancing**
* Move partitions gradually.
* Use consistent hashing.
* Pre-split partitions.

---

### **Leader Election**
* Choosing a leader node for coordination.
* Tools: ZooKeeper, etcd, Raft.

---

### **MVCC (Multi-Version Concurrency Control)**
* Allows concurrent reads/writes without locking.

---

### **N+1 Select Problem**
* Too many small queries instead of a batch, causing performance degradation.

---

### **Quorum**
* Minimum number of nodes that must agree for an operation to succeed.

---

### **Raft**
* Consensus algorithm that is simpler than Paxos.

---

### **Read Repair**
* Fix stale replicas during reads.

---

### **Replication Models**
* **Single-leader**
* **Multi-leader**
* **Leaderless**

---

### **Split-brain**
* Two nodes both think they are leaders, causing data divergence.

---

### **2PC (Two-Phase Commit)**
* Prepare phase → Commit phase for distributed transactions.
* Blocking protocol.

---

### **3PC (Three-Phase Commit)**
* Adds an extra phase to reduce blocking.

---

### **WAL (Write-Ahead Log)**
* Log changes before applying them to ensure durability.

---

### **Write & Read Amplification**
* Write amplification – More writes to disk than requested.
* Read amplification – Reads involve more data than needed.
