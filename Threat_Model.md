# Threat Model — Scoops2Go Secure REST API

## 1. Overview
This document identifies, evaluates, and mitigates potential security threats to the Scoops2Go REST API.

### System Description
The Scoops2Go API allows customers to browse, order, and pay for frozen desserts. It interacts with:
- **Frontend Client** – used by customers and drivers.
- **Database** – stores orders, users, and product data.
- **Admin Panel** – used by business staff for management.

All communications occur over HTTPS.

## 2. Assets to Protect
| Asset | Description | Confidentiality | Integrity | Availability |
|--------|--------------|----------------|-----------|--------------|
| User credentials | Login details and tokens | High | High | Medium |
| Payment data | Card or transaction details | High | High | Medium |
| Order data | Order history and delivery info | Medium | High | Medium |
| API keys | Backend secrets for third-party services | High | High | Medium |

## 3. Threat Identification (STRIDE Model)
| Threat Type | Example | Mitigation |
|--------------|----------|-------------|
| **Spoofing** | Attacker pretends to be a valid user | Enforce JWT authentication and MFA |
| **Tampering** | API payload modified in transit | Use HTTPS and digital signatures |
| **Repudiation** | Users deny actions | Implement audit logging with timestamps |
| **Information Disclosure** | Sensitive data leaked | Encrypt data at rest and sanitize responses |
| **Denial of Service (DoS)** | API overwhelmed | Apply rate limiting and WAF rules |
| **Elevation of Privilege** | Normal user gains admin access | Enforce role-based access control (RBAC) |

## 4. Threat Diagram
*(Insert threat model diagram below — system components, data flows, and trust boundaries)*

## 5. Security Controls Summary
- HTTPS enforced
- JWT with short expiry
- Parameterized queries
- API gateway with throttling
- CI/CD vulnerability scans (CodeQL)
- Encrypted database fields for PII

## 6. Review
Threat model will be reviewed after each code update or new feature.
