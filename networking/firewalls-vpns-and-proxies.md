## Firewalls, VPNs and Proxies

Firewalls, VPNs and proxies control **who can communicate**,
**how traffic is protected**, and **where access is allowed**.
They form the defensive perimeter of modern networks.

---

## Firewalls

A firewall filters network traffic based on rules.

### What firewalls inspect
- Source and destination IP
- Ports
- Protocols
- Direction (inbound / outbound)
- Application data (for advanced firewalls)

---

## Types of Firewalls

### Packet-Filtering Firewalls
- Inspect packet headers only
- Fast but limited
- No session awareness

### Stateful Firewalls
- Track active connections
- Allow return traffic automatically
- More secure than stateless filtering

### Host-Based Firewalls
- Run on individual servers or endpoints
- Protect a single system

### Next-Generation Firewalls (NGFW)
- Inspect Layer 7 traffic
- Detect applications, malware, and anomalies
- Perform deep packet inspection

---

## Firewall Rules & Policies

Common best practices:
- Block all inbound traffic by default
- Allow only required ports and IPs
- Restrict management access (SSH, RDP)
- Block risky protocols (SMB, Telnet)
- Log and monitor denied traffic

---

## Virtual Private Networks (VPN)

A VPN creates an encrypted tunnel across untrusted networks.

### Why VPNs matter
- Secure remote access
- Protect data on public Wi-Fi
- Hide internal IP addresses
- Enforce access control

---

## VPN Protocols

- **IPSec**: Enterprise-grade, complex, stable
- **OpenVPN**: Flexible, TLS-based, widely used
- **WireGuard**: Modern, fast, minimal codebase

---

## VPN Security Concepts

- Tunneling
- Encryption
- Authentication
- Integrity
- Full tunnel vs split tunneling

---

## Proxies

A proxy acts as an intermediary between clients and servers.

### Proxy benefits
- Hide internal IP addresses
- Control outbound access
- Log and inspect traffic
- Filter malicious destinations

---

## Proxy Types

- Forward proxy (protects clients)
- Reverse proxy (protects servers)
- Transparent proxy (silent filtering)
- SOCKS5 proxy (protocol-agnostic)

---

## VPN vs Proxy

| Feature | VPN | Proxy |
|------|----|------|
| Encrypts traffic | Yes | No |
| Protects all apps | Yes | No |
| Hides IP | Yes | Yes |
| Security focus | High | Limited |

---

## Zero Trust Network Access (ZTNA)

ZTNA replaces broad network access with
application-specific access.

### Core principles
- Never trust by default
- Verify continuously
- Minimize access scope
- Reduce lateral movement

---

## Why This Matters

Firewalls block threats.
VPNs secure connections.
Proxies control visibility.

Together, they define modern network security.
