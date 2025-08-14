## Network

---

### **ARP Protocol (Address Resolution Protocol)**
* **Purpose**: Maps an IP address (logical) to a MAC address (physical) within a local network.
* Works at **Layer 2 (Data Link)** and **Layer 3 (Network)** of the OSI model.
* **Example**:
  - You want to send a packet to `192.168.1.15` on your LAN.
  - Your system sends a broadcast ARP request: *"Who has 192.168.1.15?"*
  - The device with that IP replies: *"It’s me, MAC 00:1A:2B:3C:4D:5E"*.
  
---

### **Bandwidth**
* **Definition**: Maximum amount of data transferable over a network in a given time (bps).
* **Example**:
  - 100 Mbps link → Max theoretical transfer = 12.5 MB/s.
  - Actual throughput is lower due to protocol overhead.

---

### **BGP (Border Gateway Protocol)**
* **Purpose**: Routing protocol that decides how packets travel between autonomous systems (AS) on the Internet.
* Works at **Layer 3 (Network)**.
* **Example**:
  - Your ISP learns the best route to reach Google’s network via BGP announcements.
  - If one path fails, BGP reroutes via another.

---

### **CoDel (Controlled Delay)**
* **Purpose**: Active queue management algorithm to prevent bufferbloat.
* Keeps packet latency low by dropping packets early when queues grow too long.
* **Example**:
  - If a router’s buffer starts holding packets too long, CoDel drops some → signals TCP senders to slow down.

---

### **CORS (Cross-Origin Resource Sharing)**
* **Purpose**: Browser security feature controlling resource sharing across domains.
* **Example**:
  - Your frontend at `https://app.com` makes an API call to `https://api.com`.
  - If `api.com` does not allow `app.com` in its `Access-Control-Allow-Origin` header, the browser blocks the request.

---

### **DNS (Domain Name System)**
* **Purpose**: Translates domain names into IP addresses.
* **Example**:
  - `google.com` → `142.250.183.14`
  - Works via recursive resolvers, root servers, TLD servers, and authoritative servers.

---

### **Ping vs. Heartbeat**
* **Ping**:
  - ICMP echo request to check reachability.
  - Example: `ping google.com` shows packet loss and latency.
* **Heartbeat**:
  - Periodic signal between systems to detect failures.
  - Example: Load balancer checks service health every 10s.

---

### **TCP (Transmission Control Protocol)**
* **Features**: Reliable, ordered, connection-oriented, error-checked.
* **Example**:
  - File downloads, web browsing (HTTP/HTTPS).
  - Uses 3-way handshake.

---

### **TCP vs. UDP**
| Feature | TCP | UDP |
|---------|-----|-----|
| Reliability | Yes | No |
| Ordering | Yes | No |
| Speed | Slower | Faster |
| Examples | HTTP, FTP | DNS, video streaming |

---

### **Congestion Control**
* **Purpose**: TCP algorithm to prevent overwhelming the network.
* **Example**:
  - TCP slow-start → gradually increases sending rate until packet loss detected.

---

### **Connection Backlog**
* **Definition**: Queue of incoming TCP connection requests waiting for acceptance.
* **Example**:
  - If backlog is full, new connections are dropped (common in high-load web servers).

---

### **Flow Control**
* **Purpose**: Prevents sender from overwhelming receiver’s buffer.
* **Example**:
  - TCP uses a "window size" to limit in-flight data.

---

### **Handshake**
* **TCP 3-Way Handshake**:
  1. Client → SYN
  2. Server → SYN-ACK
  3. Client → ACK
* **Example**:
  - Establishing connection before sending HTTP requests.

---

### **HTTP**
* **Definition**: Application layer protocol for web communication.
* **Example**:
  - Request: `GET /index.html HTTP/1.1`
  - Response: HTML file.

---

### **HTTP/2**
* **Features**:
  - Multiplexing (multiple requests over one TCP connection).
  - Header compression.
* **Example**:
  - Web pages with many assets load faster compared to HTTP/1.1.

---

### **Head-of-Line (HOL) Blocking**
* **Problem**:
  - In HTTP/1.1, one slow request blocks others in the same connection.
* **Example**:
  - One large image delays smaller CSS/JS files.

---

### **Health Checks: Passive vs. Active**
* **Active**: System proactively sends requests to check service status.
  - Example: Load balancer sends `/health` request every 5s.
* **Passive**: Observes real traffic for failures.
  - Example: If user requests fail, mark backend unhealthy.

---

### **Internet Model**
* **Layers**: Link → Internet → Transport → Application.
* **Example**:
  - Ethernet (Link) → IP (Internet) → TCP (Transport) → HTTP (Application).

---

### **NTP (Network Time Protocol)**
* **Purpose**: Synchronizes clocks between systems.
* **Example**:
  - Server syncs with `pool.ntp.org` to ensure timestamps match across logs.

---

### **OSI Model**
| Layer | Example |
|-------|---------|
| 7 – Application | HTTP, DNS |
| 6 – Presentation | SSL/TLS |
| 5 – Session | RPC |
| 4 – Transport | TCP, UDP |
| 3 – Network | IP |
| 2 – Data Link | Ethernet |
| 1 – Physical | Fiber, copper cables |

---

### **Routers**
* **Purpose**: Connects multiple networks, routes packets.
* **Example**:
  - Home router connects LAN to the Internet.

---

### **Switch**
* **Purpose**: Connects devices in the same network, forwards frames based on MAC addresses.
* **Example**:
  - Office Ethernet switch connecting multiple PCs.

---

### **Network Topologies**
* **Types**:
  - Star, Mesh, Bus, Ring.
* **Example**:
  - Star topology: Home Wi-Fi network with all devices connected to one router.

---

### **What Happens if You Type google.com in Your Browser**
1. **DNS lookup** → Get IP for `google.com`.
2. **TCP handshake** → Connect to Google server.
3. **TLS handshake** → Establish secure channel (HTTPS).
4. **HTTP request** → `GET /`.
5. **Server responds** → HTML + assets.
6. **Browser renders** → Shows page.

---
