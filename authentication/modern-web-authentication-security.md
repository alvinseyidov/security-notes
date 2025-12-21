# Modern Web Authentication Security  
### JWT, Cookies, CSRF, SSRF & Common Developer Mistakes

> Developer-focused security notes on how authentication systems fail in the real world, why common implementations break, and how attackers abuse design mistakes.

---

## Why This Exists

Authentication is the **most common failure point** in web applications.

Attackers rarely break cryptography.  
They bypass authentication logic.

This document collects **practical security lessons** from:
- Real-world attack patterns
- OWASP Top 10
- Secure backend design
- Hands-on Django implementation

---

## Core Topics Covered

- Sessions vs stateless authentication
- Cookies vs Authorization headers
- JWT access tokens vs refresh tokens
- Token rotation & reuse detection
- XSS, CSRF, and SSRF threat models
- HttpOnly cookies and SameSite policies
- OAuth vs authentication (OIDC)
- Brute-force protection & audit logging
- Common developer mistakes

---

## Sessions, Cookies & Tokens (Mental Models)

**Sessions**  
Server remembers you.

**Tokens**  
You carry proof of identity.

**Cookies**  
Sent automatically by the browser.

**Headers**  
Sent manually by JavaScript.

Each choice changes the attack surface.

---

## XSS: How Tokens Get Stolen

If JavaScript can read it, **XSS can steal it**.

Unsafe:
- localStorage
- sessionStorage
- JS variables

Safe:
- HttpOnly cookies

HttpOnly prevents JavaScript access even if XSS exists.

---

## CSRF vs SSRF (Common Confusion)

| | CSRF | SSRF |
|--|-----|------|
| Who is tricked | Browser | Server |
| Attack surface | User session | Backend services |
| Target | Authenticated endpoints | Internal APIs, metadata |

CSRF tokens **do not** protect against SSRF.

---

## Access Tokens vs Refresh Tokens

| Token | Lifetime | Purpose |
|------|----------|--------|
| Access Token | Minutes | API authorization |
| Refresh Token | Days | Issue new access tokens |

Rules:
- Access tokens → short-lived, memory only
- Refresh tokens → HttpOnly cookies
- Refresh tokens must be rotated

---

## Why JWT Authentication Fails

JWT is not insecure.  
**Bad implementations are.**

Common failures:
- Long-lived access tokens
- No refresh token rotation
- No revocation mechanism
- No audit logging
- Tokens treated like sessions

JWTs are credentials — treat them like passwords.

---

## Token Rotation & Reuse Detection

Each refresh:
- Invalidates the old token
- Issues a new one
- Links old → new for audit

If a revoked token is reused:
- Token theft is detected
- All sessions are revoked
- Incident is logged

Without rotation → silent compromise  
With rotation → detectable attack

---

## Cookies vs Headers: XSS vs CSRF Trade-off

| Storage | XSS Risk | CSRF Risk |
|------|----------|-----------|
| localStorage | High | None |
| HttpOnly Cookie | None | Requires protection |

Mitigations:
- CSRF tokens
- SameSite=Lax
- Limited cookie path

---

## Why Logout Must Always Succeed

Logout must be **idempotent and silent**.

If logout behaves differently for valid vs invalid tokens:
- Token existence can be inferred
- Attackers gain signal

Security prefers silence over correctness.

---

## OAuth Is Not Authentication

OAuth answers:
> “Can this app access this resource?”

It does **not** answer:
> “Who is this user?”

That is OpenID Connect (OIDC).

Never treat OAuth access tokens as proof of identity.

---

## Brute Force & Audit Logging

Security is not only cryptography.

Critical controls:
- Rate limiting
- Account lockout
- Generic error messages
- Authentication audit logs

If you don’t log auth events, you won’t know you were breached.

---

## Admin Authentication Is Different

Admin access should rely on:
- IP allowlists
- VPN / Zero Trust
- Private networks
- Reverse proxy restrictions
- Strong MFA

Admin ≠ user authentication.

---

## Backed by Real Implementation

These notes are backed by a Django project implementing:

- Argon2 password hashing
- JWT access & refresh tokens
- Refresh token hashing & rotation
- Token reuse detection
- HttpOnly cookies
- CSRF protection
- Brute-force protection
- Authentication audit logging

This is **defensive security by design**, not theory.

---

## Final Thought

Security is not about perfection.

It’s about:
- Limiting blast radius
- Detecting failure early
- Responding correctly

Ask:
> “When this breaks, how will I know?”

---

**Status:** Active learning notes  
**Audience:** Backend developers, AppSec engineers, security learners  
