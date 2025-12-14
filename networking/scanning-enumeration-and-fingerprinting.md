## Scanning, Enumeration and Fingerprinting

Before testing or defending a system, it must be understood.
Scanning, enumeration and fingerprinting build a map of
what exists, what is exposed, and how systems behave.

These steps are foundational in both offensive and defensive security.

---

## Scanning

Scanning discovers hosts, ports and basic network exposure.

### What scanning answers
- Which systems are alive
- Which ports are open
- How the network responds to probes

### Common scanning techniques
- Host discovery (ICMP, ARP)
- TCP SYN scanning
- UDP scanning

---

## Port States

### Open
- Service is running
- Accepts connections

### Closed
- Host is reachable
- No service on that port

### Filtered
- Firewall or router blocks traffic
- Port state is intentionally hidden

---

## Enumeration

Enumeration collects detailed information from exposed services.

### Examples
- Banner grabbing
- Service version detection
- Protocol behavior
- User or resource listing (when permitted)

Enumeration reveals context and configuration details.

---

## Fingerprinting

Fingerprinting identifies the system behind a service.

### What can be fingerprinted
- Operating system
- Application stack
- Frameworks
- TLS configuration
- TCP/IP behavior

### Methods
- Active fingerprinting (sending probes)
- Passive fingerprinting (listening to traffic)

---

## Scanning Techniques

### TCP SYN Scan
- Fast and common
- Half-open connection
- Less noisy than full connections

### UDP Scan
- Slow and unpredictable
- Important for discovering hidden services

---

## Network Mapping Tools

### Nmap
- Detailed scanning
- Service and OS detection
- Script-based enumeration

### Masscan
- Extremely fast discovery
- Large-scale scanning

### RustScan
- Combines speed with Nmap analysis
- Efficient and beginner-friendly

---

## Web Fingerprinting

Web systems reveal clues through:
- HTTP headers
- Cookies
- URL patterns
- TLS configuration
- Page source and JavaScript

These signals identify frameworks and technologies.

---

## Enumeration vs Vulnerability Scanning

### Enumeration
- Observes information systems expose
- Builds understanding and context

### Vulnerability Scanning
- Matches findings to known weaknesses
- Identifies potential risk

Enumeration always comes first.

---

## Detection and Stealth

Security controls detect scanning patterns.

### Common defenses
- Firewalls
- IDS / IPS
- Rate limiting

### Evasion techniques
- Slow scans
- Randomized ports
- Rate control
- Decoys

Understanding evasion helps defenders tune detection.

---

## Legal and Ethical Rules

- Scanning without permission may be illegal
- Always define scope and authorization
- Avoid service disruption
- Follow responsible disclosure practices

---

## Why This Matters

Scanning reveals exposure.
Enumeration reveals configuration.
Fingerprinting reveals identity.

Together, they define the attack surface.
