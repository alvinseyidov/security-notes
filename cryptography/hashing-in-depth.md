## Hashing in Cybersecurity (In Depth)

Hashing is a one-way cryptographic operation used to verify integrity
and protect sensitive data without revealing the original value.

Hashing is fundamental to password security, digital signatures,
and many authentication systems.

---

## Core Concepts

### Message Digest
- The fixed-length output produced by a hash function
- Acts as a unique fingerprint of the input data

### Collision Resistance
- Property that makes it infeasible to find two inputs
  that produce the same hash
- Essential for security-related use cases

---

## Common Hash Algorithms

### MD5
- Cryptographically broken
- Collisions are trivial to generate
- Must never be used for security

### SHA-1
- Deprecated and insecure
- Collision attacks are practical

### SHA-2 (SHA-256, SHA-512)
- Widely used and secure
- Common in certificates, signatures, and integrity checks

### SHA-3
- Newer standard with different internal design
- Resistant to known attack classes

---

## Password Hashing

Passwords must never be stored using fast hash functions alone.

### Salt
- Random value added before hashing
- Prevents rainbow table attacks
- Must be unique per password

### Pepper
- Secret value stored separately from the database
- Adds an additional layer of protection

---

## Rainbow Tables

- Precomputed tables mapping hashes to original inputs
- Effective only against unsalted hashes
- Completely mitigated by proper salting

---

## Slow Hashing Algorithms

Designed to be intentionally slow to resist brute-force attacks.

### bcrypt
- Automatically applies salt
- Adjustable cost factor
- Widely supported and secure

### Argon2
- Memory-hard design
- Resistant to GPU and ASIC attacks
- Recommended modern standard

---

## Key Derivation Functions (KDFs)

KDFs transform weak secrets into strong cryptographic keys.

### KDF2
- Standardized key derivation function
- Uses repeated hashing to strengthen input secrets

### PBKDF2
- Uses salt and many iterations
- Commonly used in:
  - Django
  - WPA2
  - Cloud services

Repeated hashing dramatically increases brute-force cost.

---

## HMAC (Hash-Based Message Authentication Code)

HMAC combines:
- A hash function
- A secret key

### What HMAC provides
- Message integrity
- Authentication

HMAC cannot be forged without the secret key.

### Use cases
- API request signing
- Session cookies
- Network protocol security

### Difference from hashing
- Hashing alone requires no secret
- HMAC requires a shared secret key

---

## Summary
- Hashing is one-way and irreversible
- Password security requires salting and slow hashing
- KDFs and HMAC extend hashing for secure systems
- Weak or fast hashes undermine entire security models
