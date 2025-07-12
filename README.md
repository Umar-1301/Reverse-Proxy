# Reverse-Proxy

🌟 Overview
This project simulates an enterprise-grade network with a secure reverse proxy setup, showcasing advanced networking and security principles in a virtual lab environment.

The main goal was to securely expose an internal web server to external users through a layered security architecture using NAT, firewalls, DNS, and routing.

✅ End Result: A successful HTTP connection from a remote user to an internal web server using the public domain shoosmiths.com, routed through a Cloudflare-style proxy firewall.

✅ Technologies and Skills Demonstrated
Static and dynamic routing

PAT (Port Address Translation)

Static NAT, Object NAT, and Twice NAT

DNS server integration for public name resolution

ASA firewall configuration

Return path routing for end-to-end packet delivery

Web server configuration

Basic HTML serving

Network segmentation: DMZ, Public, Private zones

🚀 Network Flow Summary
A user types shoosmiths.com into their browser.

The DNS query is sent to a public DNS server (8.8.8.8), which resolves the domain to 170.40.20.2.

The Edge Router receives the request and performs PAT, translating the destination to 172.16.10.1.

Traffic is forwarded to the ASA Firewall, which is listening on 172.16.10.2.

The ASA performs Static NAT, forwarding the request to the internal web server at 192.168.1.2.

The web server serves the HTML page:
Hello, welcome to Shoosmiths.

The return traffic follows the reverse NAT and routing path, successfully reaching the user.
