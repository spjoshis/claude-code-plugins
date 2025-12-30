---
name: threat-modeling
description: Master threat modeling with STRIDE, attack trees, risk assessment, and identifying security threats in systems and applications.
---

# Threat Modeling

Systematically identify and assess security threats using structured methodologies like STRIDE to build more secure systems.

## When to Use This Skill

- New system design
- Feature development
- Architecture changes
- Security reviews
- Risk assessment
- Compliance requirements
- Incident prevention
- Security training

## Core Concepts

### 1. STRIDE Methodology

```markdown
**S - Spoofing**: Impersonating someone/something
**T - Tampering**: Modifying data or code
**R - Repudiation**: Denying actions
**I - Information Disclosure**: Exposing information
**D - Denial of Service**: Denying service to users
**E - Elevation of Privilege**: Gaining unauthorized access
```

### 2. Threat Model Example

```markdown
# Threat Model: User Authentication System

## System Overview
Web application with username/password authentication, session management, and password reset functionality.

## Assets
- User credentials (usernames, password hashes)
- Session tokens
- User personal data
- Password reset tokens

## Entry Points
1. Login page
2. Password reset page
3. API endpoints
4. Database

## Trust Boundaries
- Client ↔ Server (HTTPS)
- Application ↔ Database
- User ↔ Application

## Threats (STRIDE Analysis)

### Spoofing
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| S1 | Credential stuffing | High | Rate limiting, MFA |
| S2 | Session token theft | High | Secure cookies, HTTPS only |
| S3 | Password reset abuse | Med | Token expiration, email verification |

### Tampering
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| T1 | SQL injection | High | Prepared statements, input validation |
| T2 | Session fixation | Med | Regenerate session on login |

### Repudiation
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| R1 | No audit trail | Low | Comprehensive logging |

### Information Disclosure
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| I1 | Plaintext passwords | Critical | Bcrypt hashing |
| I2 | Verbose error messages | Med | Generic error responses |

### Denial of Service
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| D1 | Brute force attacks | High | Account lockout, CAPTCHA |
| D2 | Resource exhaustion | Med | Rate limiting |

### Elevation of Privilege
| ID | Threat | Impact | Mitigation |
|----|--------|--------|------------|
| E1 | Broken access control | High | Role-based access control |
| E2 | Insecure direct object refs | High | Authorization checks |

## Risk Rating
- Critical: Immediate remediation
- High: Fix before release
- Medium: Fix in next sprint
- Low: Track for future

## Action Items
1. Implement MFA (S1)
2. Add SQL injection prevention (T1)
3. Implement comprehensive logging (R1)
4. Verify password hashing (I1)
5. Add rate limiting (D1, D2)
```

## Best Practices

1. **Early in SDLC** - Design phase, not after
2. **Collaborative** - Developers, architects, security
3. **Document threats** - Track and prioritize
4. **Update regularly** - As system evolves
5. **Focus on high risk** - Impact and likelihood
6. **Actionable mitigations** - Specific controls
7. **Tool-supported** - Microsoft Threat Modeling Tool
8. **Link to requirements** - Security requirements from threats

## Resources

- **Threat Modeling: Designing for Security**: Adam Shostack
- **Microsoft Threat Modeling Tool**: Free tool
- **OWASP Threat Modeling**: https://owasp.org/www-community/Threat_Modeling
