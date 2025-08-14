Example: SLO = 99.9% uptime → Error budget = 0.1% downtime allowed.
* Uses:
- Decide **deployment risk**: If budget is low, slow down releases.
- Prioritize reliability work over new features.
- Communicate trade-offs between speed and stability.

---

### **SLO**
* **Key Properties**:
- Must be **measurable** via telemetry.
- Should reflect **user experience**, not just system health.
- Always time-bound (e.g., per month, per quarter).
* **Types**:
- **Availability SLO**: % of requests without errors.
- **Latency SLO**: % of requests completed under X ms.
- **Quality SLO**: % of successful transactions.
- **Durability SLO**: % of data retained without loss.

---

### **Difference Between KPIs and SLOs**
| KPI (Key Performance Indicator) | SLO (Service Level Objective) |
|----------------------------------|--------------------------------|
| Measures *any* business/system metric | Measures *reliability* from user’s POV |
| Can be operational, financial, marketing | Always about service quality |
| May not be time-bound | Always time-bound |
| Often used for trend analysis | Used to make reliability trade-offs |

---

### **Benefits of Having Alerts Based on SLOs**
* Reduces **alert fatigue** by focusing on user-impacting events.
* Improves **incident prioritization** — alerts trigger only when SLO is at risk.
* Ensures that **business goals** drive operational responses.
* Helps teams balance **feature velocity** and **stability**.

---

### **Why Exceeding an SLO is Not Necessarily Good**
* Example: Target = 99.9%, Actual = 100% uptime for months.
* Risks:
- **Over-investment** in reliability → Wasted engineering effort.
- Opportunity cost → Could have released more features.
- Error budget unused → Team is playing **too safe**.

---

### **SLO for Data**
* **Freshness**: Data is up-to-date within X minutes.
* **Completeness**: % of expected records present.
* **Consistency**: All replicas have the same data state.
* **Durability**: Data retained without corruption.

---

### **SLO for Mobiles**
* **App availability**: % of successful launches.
* **Crash rate**: < X% per session.
* **Sync latency**: Time to update server data.
* **Battery impact**: Average % consumption over a session.

---

### **SLO for Services**
* **Availability**: % of requests served without errors.
* **Latency**: p95 or p99 response time.
* **Throughput**: Requests per second sustained.
* **Error rate**: % of 5xx or 4xx errors.
* **Durability**: % of successful writes that remain valid over time.
