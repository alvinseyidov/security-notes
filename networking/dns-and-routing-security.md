## DNS and Routing in Cybersecurity

DNS and routing determine **where traffic goes** and **how it gets there**.
Because of this, they are frequent targets for attackers.

If DNS or routing is compromised, attackers can redirect,
intercept, or disrupt traffic without touching applications.

---

## Domain Name System (DNS)

DNS translates domain names into IP addresses and
stores metadata about how domains behave.

### Why DNS matters for security
- Redirects users to destinations
- Controls email routing
- Influences load balancing and CDNs
- Often abused for malware communication

---

## Common DNS Record Types & Risks

- **A / AAAA**: Domain → IP  
  Risk: traffic redirection

- **CNAME**: Domain alias  
  Risk: inherited compromise

- **MX**: Mail servers  
  Risk: email spoofing and interception

- **TXT**: SPF, DKIM, DMARC  
  Risk: weak email authentication

- **NS**: Authoritative DNS servers  
  Risk: full domain takeover

- **CAA**: Allowed certificate authorities  
  Risk: unauthorized certificate issuance

---

## DNS Resolution Process

1. Local cache check
2. Resolver query
3. Root DNS server
4. TLD server
5. Authoritative server
6. Response cached and returned

### Security note
Each step can be abused through spoofing,
cache poisoning, or forged responses.

---

## DNS Attacks

- Cache poisoning
- DNS spoofing
- DNS hijacking
- Rogue DNS servers
- DNS tunneling
- Domain shadowing
- DNS amplification (DDoS)

DNS was designed for speed, not security.

---

## Routing Fundamentals

Routing moves packets between networks using IP addresses.
Routers forward packets based on routing tables.

Routing operates at **Layer 3**.

---

## IP Addressing, Subnets & CIDR

- Public IPs are internet-facing
- Private IPs remain internal
- Subnets divide networks into isolated segments
- CIDR defines network size and exposure

### Security relevance
- Limits lateral movement
- Controls access between systems
- Reduces attack surface

---

## Border Gateway Protocol (BGP)

BGP connects independent networks across the internet.
It announces which IP ranges belong to which networks.

### Security issues
- No built-in authentication
- Trust-based by design

### Common attacks
- BGP hijacking
- Route leaks
- Traffic interception
- Blackholing routes

---

## Routing Attacks

- Man-in-the-middle via routing manipulation
- ICMP redirect abuse
- Malicious or misconfigured static routes
- Internal route manipulation

---

## Why This Matters

DNS decides the destination.
Routing decides the path.

Compromising either allows attackers to:
- Redirect users
- Intercept traffic
- Hide malware communication
- Disrupt availability
