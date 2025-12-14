## Encoding vs Hashing vs Encryption

These three concepts are often confused but serve very different purposes
in cybersecurity and application security.

---

## Encoding

Encoding changes data representation so systems can process or transmit it.
It does **not** provide security.

### Common encoding formats
- Base64
- URL encoding
- ASCII
- UTF-8

### Use cases
- Transmitting binary data over text-based systems
- Ensuring URLs and requests do not break
- Standardizing character representation

### Security note
- Encoded data can always be decoded
- Encoding must never be used to protect secrets or passwords

---

## Hashing

Hashing is a **one-way** operation.
Original data cannot be recovered from the hash.

### Common hashing algorithms
- SHA-256 (secure)
- SHA-1 (deprecated)
- MD5 (broken)

### Use cases
- Password storage
- Integrity checks
- Digital signatures
- Blockchain systems

### Password security best practices
- Never store plain hashes
- Always use:
  - Salt
  - Slow hashing algorithms (bcrypt, Argon2, PBKDF2)

### Security note
Fast hashes allow attackers to brute-force billions of guesses per second.

---

## Encryption

Encryption protects data by transforming it into unreadable form
that can be reversed using a key.

### Symmetric encryption
- Same key for encryption and decryption
- Example: AES
- Used for:
  - Disk encryption
  - VPNs
  - WiFi security

### Asymmetric encryption
- Public key encrypts
- Private key decrypts
- Examples: RSA, ECC
- Used for:
  - HTTPS
  - Certificates
  - Secure key exchange

---

## Real-world usage

### Login systems
- Passwords are hashed before storage
- Data in transit is encrypted (TLS/HTTPS)
- Tokens may use encoding (Base64 in JWT)

### File downloads
- Hashes verify file integrity
- Encryption protects transfer
- Metadata may be encoded

### API authentication
- Tokens are encoded for transport
- Hashing verifies signatures (HMAC)
- Encryption protects communication

---

## Common developer mistakes
- Treating Base64 as security
- Using MD5 or SHA-1 for passwords
- Storing passwords without salt
- Encrypting data without key management
- Mixing encoding with hashing

---

## Quick summary
- Encoding = representation
- Hashing = verification
- Encryption = protection
