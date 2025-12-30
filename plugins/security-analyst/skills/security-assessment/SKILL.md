---
name: security-assessment
description: Master security assessments with vulnerability scanning, penetration testing, security testing, and security audits.
---

# Security Assessment

Conduct comprehensive security assessments to identify vulnerabilities, test security controls, and improve security posture.

## When to Use This Skill

- Pre-release security testing
- Compliance audits
- Vulnerability management
- Security validation
- Third-party assessments
- Incident prevention
- Security baseline
- Continuous monitoring

## Core Concepts

### 1. Vulnerability Assessment

```markdown
## Vulnerability Scan Report

**Scan Date**: 2024-01-15
**Target**: web.example.com
**Tool**: Nessus

### Critical Vulnerabilities (2)
1. **CVE-2023-XXXXX**: SQL Injection in login form
   - CVSS: 9.8 (Critical)
   - Remediation: Update framework to v2.1.5
   - Priority: P0

2. **CVE-2023-YYYYY**: RCE in file upload
   - CVSS: 9.1 (Critical)
   - Remediation: Implement file type validation
   - Priority: P0

### High Vulnerabilities (5)
3. **Missing Security Headers**
   - Missing: CSP, X-Frame-Options, HSTS
   - CVSS: 7.5
   - Remediation: Configure headers in web server

4. **Weak TLS Configuration**
   - TLS 1.0/1.1 enabled
   - CVSS: 7.4
   - Remediation: Disable old TLS versions

### Remediation Plan
- Week 1: Fix critical issues (1, 2)
- Week 2: Fix high severity (3, 4, 5)
- Week 3: Rescan and verify
```

### 2. Security Test Plan

```markdown
# Security Test Plan: E-Commerce Application

## Scope
- Web application
- API endpoints
- Mobile apps (iOS/Android)

## Test Categories

### Authentication & Session Management
- [ ] Brute force protection
- [ ] Password complexity
- [ ] Session timeout
- [ ] Secure session tokens
- [ ] MFA implementation
- [ ] Password reset security

### Authorization
- [ ] Horizontal privilege escalation
- [ ] Vertical privilege escalation
- [ ] Insecure direct object references
- [ ] Missing function-level access control

### Input Validation
- [ ] SQL injection
- [ ] XSS (reflected, stored, DOM)
- [ ] Command injection
- [ ] Path traversal
- [ ] XXE

### Cryptography
- [ ] Sensitive data encryption (in transit)
- [ ] Sensitive data encryption (at rest)
- [ ] Weak cryptographic algorithms
- [ ] Insecure random number generation

### Business Logic
- [ ] Payment bypass
- [ ] Cart manipulation
- [ ] Price tampering
- [ ] Inventory manipulation

### API Security
- [ ] API authentication
- [ ] Rate limiting
- [ ] Input validation
- [ ] Error handling

## Test Approach
1. Automated scanning (OWASP ZAP)
2. Manual testing (Burp Suite)
3. Code review (key areas)
4. Configuration review
```

## Best Practices

1. **Get permission** - Authorization before testing
2. **Define scope** - Clear boundaries
3. **Use multiple methods** - Automated + manual
4. **Document findings** - Clear, reproducible
5. **Prioritize by risk** - CVSS + business impact
6. **Verify fixes** - Retest after remediation
7. **Safe testing** - Avoid service disruption
8. **Continuous assessment** - Regular scanning

## Resources

- **OWASP Testing Guide**: Comprehensive testing methodology
- **Burp Suite**: Web security testing tool
- **OWASP ZAP**: Free security scanner
