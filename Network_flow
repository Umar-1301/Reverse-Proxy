## 🔁 Network Flow Summary (End-to-End)

### 1. User Initiates a Connection
A user on the public network enters `shoosmiths.com` in their browser. This request needs to resolve the domain name to an IP address.

### 2. DNS Resolution
The request is sent to a public DNS server (`8.8.8.8`), which maps `shoosmiths.com` to a public IP address — specifically the Cloudflare firewall’s IP (e.g., `160.50.10.1`).

### 3. Cloudflare Firewall (Reverse Proxy)
- This public IP is hosted on a simulated Cloudflare firewall.
- Traffic is **filtered**, **inspected**, and either **accepted or rejected** before reaching internal resources.
- It acts as a **reverse proxy**, masking the internal server and reducing the attack surface.

### 4. Forward to Internal Network
After verification, Cloudflare forwards the HTTP request toward the internal web server via:
- **Cloud Router → NAT Gateway → Network Edge Router**

### 5. Network Edge Router (PAT)
The `Network_Edge_Router` is configured with **PAT (Port Address Translation)**.
- Any requests targeting public IP `170.40.20.2` are translated and sent internally to `172.16.10.2`.

### 6. ASA Firewall (Static NAT)
The **ASA firewall** receives traffic on `172.16.10.2` and performs **Static NAT**, translating it to the actual internal web server IP `192.168.1.2`.

This ensures the server is reachable **without exposing its real internal IP** to the outside world.

### 7. Web Server (Response)
- The web server at `192.168.1.2` serves the HTML content:  
  **"Hello, welcome to Shoosmiths."**

- The return traffic follows the reverse path:  
  **ASA → Network_Edge_Router → NAT Gateway → Cloudflare → ISP → User**
