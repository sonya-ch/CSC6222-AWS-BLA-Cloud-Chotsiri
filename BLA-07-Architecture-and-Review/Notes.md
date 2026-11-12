# BLA7 – AWS Architecture Notes

## 1. AWS Well-Architected Framework

Remember the **6 Pillars**:

| Pillar | Key Idea |
|---|---|
| Operational Excellence | Run and monitor systems; continuously improve |
| Security | Protect data, systems, and resources |
| Reliability | Recover from failures and maintain availability |
| Performance Efficiency | Use resources efficiently and adapt to demand |
| Cost Optimization | Avoid unnecessary costs |
| Sustainability | Reduce environmental impact |

**Exam Memory:**
- Security = Protect
- Reliability = Recover
- Performance = Efficient
- Cost = Save money
- Sustainability = Reduce environmental impact
- Operational Excellence = Operate and improve

## 2. AWS Global Infrastructure

| Component | Meaning |
|---|---|
| Region | Separate geographical area |
| Availability Zone (AZ) | One or more isolated data centres within a Region |
| Edge Location | Location used to deliver content closer to users |

**Exam Memory:**
- Region = Where AWS resources are located.
- AZ = Provides high availability and fault isolation.
- Edge Location = Faster content delivery using CloudFront.

## 3. High Availability vs. Fault Tolerance

**High Availability (HA)**
- Keeps applications running with minimal downtime.
- Uses multiple Availability Zones.
- Helps reduce service interruptions.

**Fault Tolerance**
- Continues operating even when a component fails.
- Requires redundancy and resilient architecture.

**Exam Memory:**
- High Availability = Minimize downtime.
- Fault Tolerance = Continue operating during failures.

## 4. Scalability vs. Elasticity

**Scalability**
- Increase or decrease resources to handle workload changes.
- Can be vertical or horizontal.

**Elasticity**
- Automatically adjusts resources based on demand.
- Adds resources when demand increases.
- Removes resources when demand decreases.

**Exam Memory:**
- Scalability = Ability to grow.
- Elasticity = Automatically adjust to demand.

## 5. AWS Security Principles

- **IAM:** Manage users, groups, roles, and permissions.
- **Least Privilege:** Give users only the permissions they need.
- **Security Groups:** Virtual firewalls for EC2 instances; stateful.
- **Network ACLs:** Control inbound and outbound subnet traffic; stateless.
- **Encryption:** Protect data at rest and in transit.
- **MFA:** Add another layer of authentication.

**Exam Memory:**
- IAM = Who can access?
- Security Group = Instance-level traffic control.
- Network ACL = Subnet-level traffic control.
- Encryption = Protect data.
- MFA = Extra login security.

## 6. AWS Shared Responsibility Model

AWS and the customer share security responsibilities.

**AWS – Security OF the Cloud**
- Physical data centres
- Hardware
- Networking infrastructure
- Virtualization infrastructure

**Customer – Security IN the Cloud**
- Data
- IAM permissions
- Operating system configuration (depending on service)
- Application security
- Network and firewall configuration

**Exam Memory:**
- AWS = Security OF the Cloud.
- Customer = Security IN the Cloud.
- Responsibility changes depending on the AWS service used.

## 7. Example: Online Shopping Architecture

A typical AWS architecture may include:

1. Route 53 – DNS and domain name resolution.
2. CloudFront – Deliver content through edge locations.
3. Application Load Balancer – Distribute incoming application traffic.
4. EC2 – Run application servers.
5. Auto Scaling – Adjust the number of EC2 instances.
6. RDS – Store relational database information.
7. S3 – Store images and static files.
8. IAM – Manage access and permissions.
9. CloudWatch – Monitor resources and application performance.

**Exam Memory:**
- Route 53 = DNS
- CloudFront = Content delivery
- Load Balancer = Distribute traffic
- EC2 = Compute
- Auto Scaling = Adjust capacity
- RDS = Relational database
- S3 = Object storage
- IAM = Access control
- CloudWatch = Monitoring

## 8. Quick Exam Revision

| Question Clue | AWS Concept / Service |
|---|---|
| Monitor metrics and create alarms | CloudWatch |
| Track API calls and account activity | CloudTrail |
| Deliver content globally with low latency | CloudFront |
| Improve availability across data centres | Multiple AZs |
| Automatically adjust capacity | Auto Scaling |
| Distribute incoming application traffic | Load Balancer |
| Manage permissions | IAM |
| Protect data at rest | Encryption |
| Resolve domain names | Route 53 |
| Store objects and files | S3 |
| Relational database | RDS |
| Reduce unnecessary cloud spending | Cost Optimization |

## 9. Final Memory Tips

- **6 Pillars:** Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability.
- **Region:** Geographical area.
- **AZ:** Isolated infrastructure within a Region.
- **Edge Location:** Content delivery closer to users.
- **High Availability:** Minimize downtime.
- **Fault Tolerance:** Continue operating during failures.
- **Scalability:** Increase or decrease capacity.
- **Elasticity:** Automatically adjust capacity.
- **Shared Responsibility:** AWS protects the cloud; customers protect what they put in the cloud.

---

**Remember:** For the AWS Certified Cloud Practitioner exam, focus on understanding the purpose of each service and identifying the correct service from a scenario.
