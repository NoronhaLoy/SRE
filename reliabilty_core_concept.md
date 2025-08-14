## Reliability & Scalability

---

### **Reliability Concepts**

#### **Availability**
* Definition: The proportion of time a system is operational and accessible.
* Measured in: Uptime percentage (e.g., 99.9%).
* Example: A service with 99.9% uptime can be down for ~8.77 hours/year.

#### **Resiliency**
* Definition: The ability of a system to recover quickly from failures.
* Focus: Recovery time and mitigation strategies.
* Example: Auto-healing Kubernetes pods after a node crash.

#### **Robustness**
* Definition: The ability to function under unexpected conditions.
* Example: Handling malformed API requests without crashing.

#### **Fault-Tolerance**
* Definition: The ability to continue functioning even if components fail.
* Example: Using redundant servers so that one server crash doesn’t stop service.

#### **Reliability**
* Definition: The probability a system performs its intended function without failure for a specific period under stated conditions.
* Scope: Combines availability, resiliency, and robustness.

---

### **Why 100% Availability is Wrong**
* **Impossible to achieve** — maintenance, upgrades, and unexpected issues will occur.
* **Trade-offs** — higher availability usually means higher costs and complexity.
* **Target realistic SLAs** — e.g., 99.95% or 99.99% uptime based on business impact.

---

### **Blast Radius**
* Definition: The scope of impact when a failure occurs.
* Goal: Reduce blast radius via segmentation, isolation, and fault domains.
* Example: Limiting a database outage to only one region instead of global.

---

### **Failure Domain**
* Definition: A set of components that can fail together due to shared dependencies.
* Examples:
  * One data center.
  * A specific Kubernetes node.
  * A single cloud availability zone.

---

### **Cascading Failures**
* Definition: A failure in one component triggering failures in dependent components.
* Example: A slow API causes all dependent services to backlog and crash.
* Prevention:
  * Circuit breakers.
  * Rate limiting.
  * Load shedding.

---

### **Hard vs. Soft Dependencies**
* **Hard dependency** — If it fails, your service fails.
  * Example: Payment gateway for checkout.
* **Soft dependency** — If it fails, the system still works with degraded features.
  * Example: Recommendation engine on a shopping site.

---

## **Scalability Concepts**

---

### **Knee Point**
* Definition: The point where adding more resources no longer yields proportional performance gains.
* Visual: Performance curve flattening.
* Action: Optimize before reaching this point.

---

### **Ceiling**
* Definition: The maximum capacity the system can handle regardless of added resources.
* Example: A database limited to 1M writes/sec due to architecture.

---

### **Number One Source of Outages**
* Complexity — The more moving parts, the higher the chance of failure.
* Keep designs simple and observable.

---

### **Tail Tolerance**
* Definition: Ability to handle slow responses from a small percentage of requests (tail latency).
* Techniques:
  * Request hedging.
  * Timeouts & retries.
  * Prioritization of critical requests.

---

### **Toil**
* Definition: Manual, repetitive work that could be automated.
* Goal: Reduce toil to increase reliability and engineering productivity.
* Examples:
  * Manual restarts of services.
  * Repeated log analysis without automation.
