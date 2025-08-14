## Cache

* **When to use a cache**
  * Use a cache when:
    * The same data is accessed repeatedly.
    * Data retrieval is expensive (e.g., complex computation, slow DB query).
    * Slightly stale data is acceptable.
  * Avoid caching when:
    * Data changes very frequently.
    * Strong consistency is critical.

---

* **Cache-aside vs. Read-through**
  * **Cache-aside (Lazy loading)**:
    * Application code first checks the cache.
    * If data is missing → fetch from source → populate cache.
    * Pros: Simple to implement.
    * Cons: First request for uncached data is slow.
  * **Read-through**:
    * Cache itself fetches data from the source when a miss occurs.
    * Application only interacts with cache.
    * Pros: Transparent to application code.
    * Cons: Cache layer becomes more complex.

---

* **Eviction policy**
  * Defines how cached entries are removed when space is needed.
  * Common policies:
    * **LRU (Least Recently Used)** – Remove least recently accessed items.
    * **LFU (Least Frequently Used)** – Remove least accessed items.
    * **FIFO (First-In, First-Out)** – Remove oldest inserted items.
    * **Random** – Remove random items (simpler, but less optimal).

---

* **Refresh-ahead**
  * Proactively refreshes data in the cache before it expires.
  * Ensures cached data is always fresh for frequent queries.
  * Prevents cache misses for popular data.

---

* **Write-through vs. Write-back**
  * **Write-through**:
    * Data is written to cache and to the source at the same time.
    * Pros: Strong consistency.
    * Cons: Higher write latency.
  * **Write-back (Write-behind)**:
    * Data is written to cache first; written to the source later (asynchronously).
    * Pros: Low write latency.
    * Cons: Risk of data loss on cache failure.

---

* **Distributed cache**
  * Cache spread across multiple nodes to:
    * Increase capacity.
    * Provide fault tolerance.
    * Handle large-scale workloads.
  * Examples: Redis Cluster, Memcached, Hazelcast.

---

* **Performance cache vs. Capacity cache**
  * **Performance cache**:
    * Main goal: Reduce latency and improve speed.
    * Usually stores hot (frequently accessed) data.
  * **Capacity cache**:
    * Main goal: Reduce backend load by storing more data.
    * Can store warm or even cold data if memory allows.
