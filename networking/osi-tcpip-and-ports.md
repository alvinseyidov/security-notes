## Networking Foundations for Cybersecurity

Networking is the foundation of cybersecurity.
Every attack, defense, and security tool relies on understanding
how systems communicate.

This document covers communication models, data flow,
ports, protocols, and their security relevance.

---

## OSI Model (Conceptual View)

The OSI model is a mental framework used to understand
where attacks and defenses operate.

### OSI Layers
- Layer 1: Physical (cables, signals)
- Layer 2: Data Link (MAC addresses, ARP)
- Layer 3: Network (IP addressing, routing)
- Layer 4: Transport (TCP, UDP, ports)
- Layer 5: Session
- Layer 6: Presentation (encryption, compression)
- Layer 7: Application (HTTP, DNS, SMTP)

### Security relevance
- ARP spoofing → Layer 2
- IP spoofing → Layer 3
- SYN flood → Layer 4
- SQL injection → Layer 7

---

## TCP/IP Model (Real-World Implementation)

The internet uses the TCP/IP model instead of OSI.

### TCP/IP Layers
- Link layer (OSI 1–2)
- Internet layer (OSI 3)
- Transport layer (OSI 4)
- Application layer (OSI 5–7)

Operating systems, routers, firewalls, and tools follow this model.

---

## Data Encapsulation & Flow

When data is sent:
- Application creates data
- Transport adds ports (TCP/UDP)
- Network adds IP addresses
- Data Link adds MAC addresses
- Physical layer sends bits

Receiving systems reverse this process (decapsulation).

### Why this matters
Attackers manipulate headers at different layers.
Firewalls and IDS inspect specific layers.

---

## Ports and Services

Ports identify which application should receive traffic.

### Common ports
- 80 / 443 → HTTP / HTTPS
- 22 → SSH
- 53 → DNS
- 25 / 587 → SMTP
- 445 → SMB

### Port ranges
- 0–1023 → Well-known
- 1024–49151 → Registered
- 49152–65535 → Dynamic (ephemeral)

---

## Protocols Every Security Engineer Must Know

- HTTP / HTTPS
- DNS
- SSH
- RDP
- SMB
- ICMP
- DHCP
- FTP / SFTP

Each protocol represents a potential attack surface.

---

## TCP vs UDP (Security Perspective)

### TCP
- Connection-oriented
- Reliable
- Used by HTTPS, SSH, email
- Targeted by SYN floods, session hijacking

### UDP
- Connectionless
- Fast, unreliable
- Used by DNS, streaming, VoIP
- Common in amplification DDoS attacks

---

## Why This Matters

Understanding OSI and TCP/IP helps:
- Map attacks to layers
- Understand firewall behavior
- Analyze packet captures
- Communicate clearly with security teams
