---
name: cloud-architecture
description: Master cloud architecture with AWS, Azure, GCP, cloud-native patterns, migration strategies, and cost optimization.
---

# Cloud Architecture

Design scalable, resilient, cost-effective cloud architectures using AWS, Azure, or GCP and cloud-native patterns.

## When to Use This Skill

- Cloud migration planning
- New cloud application design
- Multi-cloud strategy
- Cost optimization
- Scalability requirements
- High availability needs
- Disaster recovery planning
- Cloud-native modernization

## Core Concepts

### 1. AWS Well-Architected Framework

```markdown
## 6 Pillars

**1. Operational Excellence**
- Infrastructure as Code (Terraform, CloudFormation)
- CI/CD automation
- Monitoring and logging
- Incident response

**2. Security**
- IAM with least privilege
- Encryption (at rest, in transit)
- Network security (Security Groups, NACLs)
- Compliance and auditing

**3. Reliability**
- Multi-AZ deployment
- Auto-scaling
- Backup and recovery
- Fault isolation

**4. Performance Efficiency**
- Right-sizing instances
- Auto-scaling policies
- Caching (CloudFront, ElastiCache)
- Database optimization

**5. Cost Optimization**
- Reserved Instances / Savings Plans
- Spot Instances
- S3 lifecycle policies
- Cost monitoring and alerts

**6. Sustainability**
- Efficient resource utilization
- Managed services
- Serverless adoption
- Region selection
```

### 2. Reference Architecture - 3-Tier Web App (AWS)

```markdown
## AWS 3-Tier Architecture

**Tier 1: Presentation**
- Route 53 (DNS)
- CloudFront (CDN)
- S3 (static hosting)
- WAF (Web Application Firewall)

**Tier 2: Application**
- Application Load Balancer
- Auto Scaling Group (EC2 or ECS)
- Multiple Availability Zones
- Security Groups

**Tier 3: Data**
- RDS Multi-AZ (PostgreSQL)
- ElastiCache (Redis)
- S3 (file storage)

**Supporting Services:**
- VPC (network isolation)
- CloudWatch (monitoring)
- Systems Manager (configuration)
- Secrets Manager (credentials)
- SNS/SQS (messaging)

**Diagram:**
```
Internet
  ↓
Route 53 → CloudFront
  ↓
Application Load Balancer
  ↓
+---+---+---+
| EC2 | EC2 | EC2 | (Auto Scaling Group)
+---+---+---+
  ↓       ↓
RDS     ElastiCache
(Multi-AZ)
```
```

### 3. Cloud Migration Strategies (6 R's)

```markdown
**1. Rehost ("Lift and Shift"):**
- Move as-is to cloud
- Fast migration
- No code changes
- Example: VM to EC2

**2. Replatform ("Lift, Tinker, and Shift"):**
- Minor optimizations
- Use managed services
- Example: Self-managed DB → RDS

**3. Refactor / Re-architect:**
- Redesign for cloud-native
- Microservices, serverless
- Highest benefit, most effort

**4. Repurchase:**
- Move to SaaS
- Example: Email server → Office 365

**5. Retain:**
- Keep on-premises (for now)
- Not ready for migration

**6. Retire:**
- Decommission unused applications

**Migration Plan:**
```
Phase 1 (Month 1-2): Low-risk apps (Rehost)
Phase 2 (Month 3-4): Databases (Replatform to RDS)
Phase 3 (Month 5-8): Core apps (Refactor gradually)
Phase 4 (Month 9-12): Legacy apps (Evaluate retain/retire)
```
```

### 4. Multi-Cloud Strategy

```markdown
## Multi-Cloud Architecture Patterns

**Best-of-Breed:**
- AWS: Compute (ECS/EKS)
- GCP: Data analytics (BigQuery)
- Azure: Enterprise integration (AD)

**Geographic Redundancy:**
- Primary: AWS us-east-1
- DR: Azure West Europe

**Vendor Diversification:**
- Avoid lock-in
- Negotiate better pricing
- Skills distribution

**Challenges:**
- Increased complexity
- Multiple billing systems
- Different tooling
- Network connectivity
- Cost tracking

**Tools:**
- Terraform (multi-cloud IaC)
- Kubernetes (portable orchestration)
- Prometheus (monitoring)
- Vault (secrets management)
```

## Best Practices

1. **Well-Architected Reviews** - Regular assessments
2. **Infrastructure as Code** - Terraform, CloudFormation
3. **Managed services first** - Reduce operational overhead
4. **Multi-AZ deployment** - High availability
5. **Auto-scaling** - Handle traffic variations
6. **Cost monitoring** - Set budgets and alerts
7. **Security by design** - IAM, encryption, network security
8. **Disaster recovery plan** - Backup, failover, testing

## Resources

- **AWS Well-Architected**: https://aws.amazon.com/architecture/well-architected
- **Azure Well-Architected**: https://docs.microsoft.com/azure/architecture/framework
- **GCP Architecture Center**: https://cloud.google.com/architecture
- **Cloud Architecture Patterns**: https://docs.microsoft.com/azure/architecture/patterns
