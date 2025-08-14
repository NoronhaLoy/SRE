## Rollout

---

### **Concepts**

---

#### **Bake Time**
* **Definition**: The waiting period after deploying a change before moving forward, used to ensure stability and catch hidden issues.
* **Example**:
  * Deploying a new API version to 10% of traffic and letting it run for **24 hours** to monitor error rates before full rollout.
* **Why It Matters**:
  * Allows catching slow-burn bugs (e.g., memory leaks, performance degradation).

---

#### **Feature Flag**
* **Definition**: A toggle that enables/disables a feature in production without redeploying code.
* **Example**:
  * Rolling out a “dark mode” UI to 5% of users by enabling the flag only for a subset of accounts.
* **Why It Matters**:
  * Allows safe rollouts, quick rollbacks, and A/B testing.

---

#### **Feature Freeze**
* **Definition**: A halt on adding new features, focusing only on stability, bug fixes, and critical changes.
* **Example**:
  * Entering feature freeze 2 weeks before a major release to ensure testing and QA.
* **Why It Matters**:
  * Prevents introducing risky changes right before deadlines.

---

#### **Rollout Supervision**
* **Definition**: Actively monitoring and controlling deployments to ensure they proceed safely.
* **Example**:
  * Having engineers on-call watching Grafana dashboards during a high-risk production rollout.
* **Why It Matters**:
  * Enables quick detection and rollback on failure.

---

### **Rollout Types**

---

#### **Blue-Green Rollout**
* **Definition**: Two identical environments (“Blue” = current, “Green” = new). Traffic is switched from blue to green in one step.
* **Example**:
  * Blue = v1.0, Green = v1.1. When v1.1 passes tests, route all traffic to Green.
* **Advantages**:
  * Zero downtime.
  * Easy rollback (switch traffic back to Blue).
* **Disadvantages**:
  * Requires double infrastructure.

---

#### **Canary Rollout**
* **Definition**: Releasing changes to a small percentage of traffic before gradually increasing exposure.
* **Example**:
  * Deploy to 5% of users → Monitor → 25% → 50% → 100%.
* **Advantages**:
  * Detects issues before full impact.
* **Disadvantages**:
  * Needs good monitoring and automation.

---

#### **Progressive Rollout**
* **Definition**: Similar to canary, but rollout increments are automated based on metrics and health checks.
* **Example**:
  * Argo Rollouts increasing deployment traffic from 5% to 100% automatically if no errors detected.
* **Advantages**:
  * Reduces manual intervention.
* **Disadvantages**:
  * Bad metrics setup can cause unsafe promotions.

---

#### **Shadow Rollout**
* **Definition**: Sending production traffic to a new version without impacting users; results are compared in the background.
* **Example**:
  * Mirroring API requests to a new backend service while still using responses from the old one.
* **Advantages**:
  * No user impact during testing.
* **Disadvantages**:
  * Doubles request processing, possible cost/performance impact.

---

### **Pro Tip**
* Combine **Feature Flags + Canary Rollouts** to minimize risk.
* Example:
  * Deploy code with feature disabled → Canary release to 5% → Enable feature via flag → Monitor → Expand rollout.
