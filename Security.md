## 🔒 Cybersecurity Links

### Reverse Proxy
A Cloudflare-style reverse proxy ensures that **attackers never interact directly with the internal web server**, acting as a secure intermediary that filters all external traffic.

### Firewall Zones
The use of a **DMZ (Demilitarized Zone)** isolates public-facing services (like the web server) from the core internal network, reducing risk of lateral movement in case of compromise.

### NAT Obfuscation
By implementing **Static NAT, PAT, and Object NAT**, **internal IP addresses are never exposed** to the public, preserving confidentiality of the internal architecture.

### Access Control
The **ASA firewall** inspects traffic and enforces rules, blocking unwanted or malicious requests. It provides **stateful inspection** and **access control policies**.

### Reduced Attack Surface
All **inbound traffic is filtered at the edge (Cloudflare firewall)** and logged, allowing only legitimate HTTP requests to proceed. This minimizes potential exploit vectors.

### DNS Exposure
Only the **essential public record (A record)** is exposed through the **public DNS server** (8.8.8.8), ensuring minimal DNS footprint and reducing discoverability by attackers.
