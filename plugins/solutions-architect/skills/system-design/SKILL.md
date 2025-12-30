---
name: system-design
description: Master system design with architecture patterns, component design, scalability planning, and creating robust, maintainable systems.
---

# System Design

Design robust, scalable systems using proven architecture patterns and best practices for enterprise applications.

## When to Use This Skill

- New system design
- Architecture refactoring
- Scaling existing systems
- Technology modernization
- Integration planning
- Performance optimization
- Architecture reviews
- Technical interviews

## Core Concepts

### 1. C4 Model Architecture Diagram

```markdown
## Level 1: System Context

[Users] → [E-Commerce System] → [Payment Gateway]
                ↓
          [Email Service]

## Level 2: Container Diagram

E-Commerce System:
- Web Application (React, Node.js)
- API Server (Node.js, Express)
- Database (PostgreSQL)
- Cache (Redis)
- Message Queue (RabbitMQ)
- Search Engine (Elasticsearch)

## Level 3: Component Diagram (API Server)

API Server:
- Authentication Service
- Product Catalog Service
- Order Management Service
- Payment Service
- Notification Service

## Level 4: Code (Authentication Service)

Classes:
- AuthController
- AuthService
- TokenManager
- UserRepository
```

### 2. Capacity Planning

```markdown
## System Capacity Planning

**Requirements:**
- 1M active users
- Peak: 10K concurrent users
- 100K transactions/day
- 3 second max response time
- 99.9% uptime

**Calculations:**

**Traffic:**
- Requests/sec (peak): 10K users × 10 req/min / 60 = 1,667 RPS
- Database queries: 1,667 × 3 avg queries = 5,000 QPS
- Storage/day: 100K × 5KB avg = 500MB/day
- Storage/year: 500MB × 365 = 180GB

**Server Capacity:**
- App servers: 1,667 RPS / 200 RPS per server = 9 servers
- With redundancy (3x): 27 servers
- Database: Master-replica setup, read replicas for queries

**Network:**
- Bandwidth: 1,667 req × 50KB avg = 83MB/s = 664 Mbps
- CDN for static assets

**Costs (AWS estimate):**
- EC2 (27 × c5.xlarge): $3,500/month
- RDS (db.r5.2xlarge): $1,200/month
- Load Balancer: $200/month
- CloudFront CDN: $500/month
- Total: ~$5,400/month
```

### 3. Trade-Off Analysis

```markdown
## Architecture Decision: Monolith vs Microservices

**Monolith:**
✅ Pros:
- Simpler deployment
- Easier local development
- Single codebase
- Simpler testing
- Lower operational overhead

❌ Cons:
- Scaling all-or-nothing
- Technology lock-in
- Longer deployment cycles
- Harder to maintain at scale

**Microservices:**
✅ Pros:
- Independent scaling
- Technology flexibility
- Team autonomy
- Fault isolation
- Faster deployments

❌ Cons:
- Complex infrastructure
- Distributed system challenges
- Network latency
- Data consistency
- Higher operational overhead

**Decision:** Start with modular monolith, extract microservices as needed
**Rationale:** Team size (5 devs), early stage, faster time-to-market
```

## Best Practices

1. **Understand requirements** - Functional and non-functional
2. **Start simple** - YAGNI (You Aren't Gonna Need It)
3. **Design for failure** - Assume components will fail
4. **Think in layers** - Presentation, business, data
5. **Loose coupling** - Minimize dependencies
6. **High cohesion** - Related functionality together
7. **Document decisions** - ADRs (Architecture Decision Records)
8. **Iterate and evolve** - Continuous improvement

## Resources

- **Designing Data-Intensive Applications**: Martin Kleppmann
- **System Design Interview**: Alex Xu
- **C4 Model**: https://c4model.com
