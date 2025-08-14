## SLI / SLO / SLA

---

### **Concepts**
* **SLI** – Service Level Indicator
  - A **quantitative metric** measuring performance or reliability from the user’s perspective.
  - Examples: request latency, availability %, error rate, throughput.
* **SLO** – Service Level Objective
  - The **target goal** for an SLI over a defined period.
  - Example: 99.9% availability over 30 days.
* **SLA** – Service Level Agreement
  - A **formal contract** between service provider and customer defining:
    - SLO targets.
    - Penalties for breaches (credits, refunds).
  - SLAs are **enforceable**, unlike SLOs.

---

### **SLI vs. SLO vs. SLA**
| Term | What it is | Who owns it | Example |
|------|------------|-------------|---------|
| SLI  | Measurement | Engineers | 99.85% availability this month |
| SLO  | Target | Product & Engineering | Target 99.9% availability over 30 days |
| SLA  | Contract | Business & Legal | 99.9% availability per month, or 10% refund |

---

### **Error Budget**
* **Definition**: The amount of **permissible unreliability** before breaching an SLO.
* Formula:
