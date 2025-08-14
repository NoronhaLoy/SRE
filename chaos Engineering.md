## Practices

---

### **Chaos Engineering**
* **Definition**: The practice of deliberately injecting failures into a system to test its resilience and recovery mechanisms.
* **Goal**:
  * Identify weaknesses before they cause real outages.
  * Improve incident response and fault tolerance.
* **Key Principles**:
  1. **Hypothesize** how the system should behave during failure.
  2. **Introduce controlled failure** (e.g., kill pods, cut network links, simulate high latency).
  3. **Observe and measure** the impact.
  4. **Improve** the system based on findings.
* **Examples**:
  * Using tools like Chaos Monkey (Netflix) to randomly terminate instances.
  * Injecting network latency or packet loss to test microservice communication.
* **Best Practices**:
  * Start small — begin in staging before production.
  * Monitor closely during experiments.
  * Automate recovery testing regularly.
