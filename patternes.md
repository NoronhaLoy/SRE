## Patterns / Anti-patterns

---

### **Bulkhead Pattern**
* **Definition**: Isolate components so a failure in one part doesn't sink the whole system (like compartments in a ship).
* **Goal**: Contain failures to a limited scope.
* **Example**: Separate thread pools for API calls to different services so one slow service doesn’t block all requests.

---

### **Circuit Breaker**
* **Definition**: Prevents a failing service from being called repeatedly, allowing it time to recover.
* **States**:
  * **Closed** — Calls pass through normally.
  * **Open** — Calls are blocked immediately (failure detected).
  * **Half-open** — Limited test calls allowed to check if recovery happened.
* **Benefit**: Reduces load and speeds up failure detection.

---

### **Exponential Backoff**
* **Definition**: Retry strategy where the wait time between retries increases exponentially (e.g., 1s, 2s, 4s, 8s).
* **Goal**: Prevent overloading a failing system.
* **Common Use**: API retries, message processing.

---

### **Jitter**
* **Definition**: Adds randomness to retry delays to avoid synchronized retry storms.
* **Example**: Instead of retrying at exactly 8s, retry between 7–9s.
* **Benefit**: Reduces thundering herd problems.

---

### **Graceful Degradation**
* **Definition**: Maintain core functionality even when parts of the system fail.
* **Example**: E-commerce site disables product recommendations when recommendation service fails, but still allows checkout.

---

### **Load Shedding**
* **Definition**: Proactively rejecting requests when the system is overloaded to protect core functionality.
* **Techniques**:
  * Prioritize important requests.
  * Drop non-critical work.
* **Example**: Dropping requests from anonymous users during peak load to ensure logged-in users are served.

---

### **Retry Amplification (Anti-pattern)**
* **Definition**: When many clients retry failed requests at the same time, amplifying load on the failing system.
* **Prevention**:
  * Use exponential backoff with jitter.
  * Limit max retries.
* **Example**: Thousands of IoT devices retrying in sync after a service outage.

---

### **Backpressure**
* **Definition**: A mechanism where the receiver signals the sender to slow down to match processing capacity.
* **Goal**: Avoid overloading consumers.
* **Example**: Kafka consumers adjusting fetch sizes based on processing rate.

---

### **Rate Limiting**
* **Definition**: Restrict the number of requests over a period to control traffic and prevent abuse.
* **Common Algorithms**:
  * Token Bucket.
  * Leaky Bucket.
  * Fixed Window.
  * Sliding Window.
* **Example**: API allowing only 100 requests/minute per user.

---

### **Request Hedging**
* **Definition**: Sending the same request to multiple replicas and using the fastest response.
* **Goal**: Reduce tail latency.
* **Trade-off**: Increases load; should be used carefully.
* **Example**: DNS queries sent to multiple resolvers to get quicker response.
