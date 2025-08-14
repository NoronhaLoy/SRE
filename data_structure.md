## Data Structures

---

### **Probabilistic Data Structures**
Used when exact answers are not required, but memory efficiency and speed are critical.  
They trade off accuracy for reduced space.

#### **Bloom Filter**
* Purpose: Test whether an element is in a set (possible false positives, no false negatives).
* Use case:  
  * Quickly checking if an item might be present before querying DB.
  * Web caching, email spam filtering.
* Pros:
  * Space-efficient.
  * Fast insert and lookup.
* Cons:
  * False positives possible.
  * Cannot remove elements (unless using counting bloom filter).

---

#### **Count-Min Sketch**
* Purpose: Estimate frequency counts of items in a data stream.
* Use case:  
  * Counting word frequencies in search engines.
  * Network traffic monitoring.
* Pros:
  * Space-efficient.
  * Works with streaming data.
* Cons:
  * Small overestimation errors.

---

#### **HyperLogLog**
* Purpose: Estimate the cardinality (number of distinct elements) of a dataset.
* Use case:
  * Counting unique visitors.
  * Analytics for large datasets.
* Pros:
  * Very memory efficient (uses ~1.5 KB for billions of items).
* Cons:
  * Approximate result.

---

### **Storage Structures**

#### **LSM Tree (Log-Structured Merge-Tree)**
* Purpose: Optimize writes in databases by batching them.
* Process:
  * Writes go to a memory table (memtable) → periodically flushed to disk as SSTables.
* Use case:
  * Write-heavy databases (e.g., Cassandra, LevelDB, RocksDB).
* Pros:
  * High write throughput.
* Cons:
  * Reads may require merging multiple files.

---

#### **B-Tree**
* Purpose: Balanced tree data structure for ordered data storage.
* Use case:
  * File systems, databases (MySQL, PostgreSQL).
* Pros:
  * Good for read-heavy workloads.
* Cons:
  * Writes are slower compared to LSM trees for large datasets.

---

#### **SSTable (Sorted String Table)**
* Purpose: Immutable, sorted key-value file stored on disk.
* Works with: LSM trees.
* Pros:
  * Sequential disk reads.
  * Efficient range scans.
* Cons:
  * Requires compaction over time.
