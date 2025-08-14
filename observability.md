## Observability

---

### **Concepts**

---

#### **What's the difference between Monitoring and Observability**
* **Monitoring**: Collecting predefined metrics to check system health (reactive).
* **Observability**: Designing systems so their internal state can be understood from external outputs (proactive).
* **Key difference**: Monitoring tells you when something is wrong; Observability helps you understand *why*.

---

#### **Trace vs. Metric vs. Log**
* **Trace**: Shows the path of a request as it travels through services (used for latency & dependency analysis).
* **Metric**: Numerical measurements over time (e.g., CPU usage, request rate).
* **Log**: Detailed event records (used for debugging).

---

#### **Golden Signals** (Google SRE)
1. **Latency** – Time taken to serve a request.
2. **Traffic** – Number of requests per second.
3. **Errors** – Rate of failed requests.
4. **Saturation** – System capacity usage.

---

#### **Observer Effect**
* Measuring a system can change its behavior.
* Example: Adding heavy logging can increase latency.

---

#### **Percentile**
* Shows distribution rather than average.
* Common: **p50** (median), **p90**, **p95**, **p99** for performance monitoring.
* Useful to detect **tail latency** issues.

---

#### **Streetlight Anti-Method**
* Only monitoring what’s easy to measure instead of what’s important.
* Example: Only checking CPU and ignoring end-to-end latency.

---

#### **Time-Series Based Monitoring Lies**
* Averages can hide problems.
* Example: 50% CPU average may actually mean half the time it’s 100% and half it’s 0%.

---

#### **USE Method** (Brendan Gregg)
* **Utilization** – How busy a resource is.
* **Saturation** – How much work is waiting.
* **Errors** – Error rates for the resource.

---

#### **Main Metrics for Cache**
* **Hit ratio** – % of requests served from cache.
* **Miss ratio** – % of requests not found in cache.
* **Eviction count** – Items removed to free space.
* **Latency** – Time to serve from cache.

---

#### **Why Should We Be Careful About Average Performance Metrics**
* Averages can hide **outliers**.
* Example: Average latency of 200ms might hide the fact that 5% of requests take 5 seconds.
