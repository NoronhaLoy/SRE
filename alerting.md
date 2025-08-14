## Alerting

---

### **Alerting Strategy**
* Define alerts based on **user impact** rather than just system metrics.
* Use **multi-level alerts**:
  - **Warning**: Early sign of degradation, not urgent.
  - **Critical**: Immediate attention required, user impact visible.
* Avoid too many alerts — focus on **actionable** signals.
* Ensure alerts include **context** for quick triage.

---

### **Alerting Fatigue Concept**
* When engineers receive too many alerts, they begin to **ignore or dismiss** them.
* Causes:
  - Too many false positives.
  - Noisy monitoring.
  - Alerts without clear action.
* Effects:
  - Reduced responsiveness.
  - Burnout.
  - Missed critical issues.

---

### **Characteristics of a Good Alert**
1. **Actionable** – Someone can do something about it.
2. **Clear** – States the problem and affected components.
3. **Relevant** – Related to current SLO/SLA.
4. **Timely** – Detected early enough to act.
5. **Prioritized** – High severity for user impact.

---

### **Slow vs. Fast Burn Alert**
* **Slow Burn**:
  - Gradual degradation over hours/days.
  - Example: Memory leak slowly increasing usage.
  - Usually **lower urgency**, more time to plan fix.
* **Fast Burn**:
  - Rapid change causing immediate impact.
  - Example: Sudden spike in error rates after deployment.
  - Requires **urgent action**.
