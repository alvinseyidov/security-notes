## TLS, PKI, and Trust Fundamentals

Modern web security relies on TLS and Public Key Infrastructure (PKI)
to provide confidentiality, integrity, and authentication.

---

## TLS (Transport Layer Security)

TLS creates a secure, encrypted connection between a client and a server.
It protects data in transit against eavesdropping and tampering.

### What TLS provides
- Confidentiality (encryption)
- Integrity (tamper detection)
- Authentication (server identity)

### SSL
- SSL is the predecessor of TLS
- SSL is deprecated and insecure
- Modern systems must use TLS only

---

## TLS Handshake (High Level)

Before encrypted data is exchanged, client and server perform a handshake.

During the handshake:
- Algorithms are negotiated
- Certificates are verified
- Keys are exchanged
- A symmetric session key is created

After this, all traffic is encrypted using a fast symmetric cipher.

---

## Cipher Suites

A cipher suite defines the exact algorithms used in a TLS session.

A modern cipher suite typically includes:
- ECDHE for key exchange
- AES-GCM for encryption
- SHA-256 for integrity

Cipher suites ensure all parties agree on secure parameters.

---

## Key Exchange

### Diffie–Hellman (DH)
- Allows secure key agreement over an insecure channel
- No secret key is transmitted directly

### Elliptic Curve Diffie–Hellman (ECDH)
- Modern variant of DH
- Smaller keys, better performance
- Widely used in modern TLS

---

## Public Key Infrastructure (PKI)

PKI is the trust system that allows devices and browsers
to verify identities on the internet.

PKI includes:
- Certificates
- Certificate Authorities (CAs)
- Trust chains
- Revocation mechanisms

PKI is a framework, not a single tool.

---

## Certificates

A certificate is a digital document that proves identity.

### Certificate contents
- Domain or entity name
- Public key
- Issuer (CA)
- Validity period
- Cryptographic signatures

### Types
- Server certificate
- Intermediate certificate
- Root certificate

---

## Trust Chain

Certificates form a chain:
- Server certificate
- Intermediate CA
- Root CA

If the root CA is trusted by the system,
all certificates below it are trusted.

---

## Certificate Authority (CA)

A CA is a trusted organization that issues certificates.
Browsers trust certificates because they trust the CA.

---

## Certificate Validity and Revocation

- Certificates expire and must be renewed
- Revoked certificates must be rejected even if not expired

### Revocation methods
- CRL (Certificate Revocation List)
- OCSP (Online Certificate Status Protocol)

---

## Special Certificate Concepts

- Self-signed certificates (trusted only manually)
- Wildcard certificates (cover subdomains)
- Certificate pinning (trust only specific keys)

---

## Summary
- TLS encrypts data in transit
- PKI provides identity and trust
- Certificates and trust chains enable secure communication
