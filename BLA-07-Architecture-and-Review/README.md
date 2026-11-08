
# AWS Architecture & Exam Review

## BLA7 AWS Cloud --- Study Guide

## Topics: AWS Well-Architected Framework, AWS Global Infrastructure, Architecture Principles, High Availability, Fault Tolerance, Scalability, Elasticity, Security, Shared Responsibility Model, and Exam Review.

### 1. Overview

AWS architecture is about designing cloud workloads that meet business
and technical requirements. The AWS Well-Architected Framework provides
best practices for evaluating and improving workloads.

  -----------------------------------------------------------------------
  Service / Concept                   Main purpose
  ----------------------------------- -----------------------------------
  AWS Well-Architected Framework      Provides best-practice guidance for
                                      designing and operating workloads

  AWS Region                          A separate geographical area where
                                      AWS operates infrastructure

  Availability Zone (AZ)              One or more discrete data centres
                                      with independent power, networking,
                                      and connectivity within a Region

  Edge Location                       A site in the AWS global network
                                      used by services such as CloudFront
                                      to deliver content closer to users

  High Availability                   Designing systems to minimise
                                      downtime and remain accessible

  Fault Tolerance                     Designing systems to continue
                                      operating when components fail

  Scalability                         Ability to increase or decrease
                                      capacity to meet workload
                                      requirements

  Elasticity                          Ability to adjust resources
                                      dynamically as demand changes

  AWS Auto Scaling                    Helps automatically adjust resource
                                      capacity according to configured
                                      policies

  Shared Responsibility Model         Defines security responsibilities
                                      shared between AWS and the customer
  -----------------------------------------------------------------------

### 2. AWS Well-Architected Framework

The AWS Well-Architected Framework is a collection of architectural best
practices and design principles. It helps organisations evaluate
workloads and make informed decisions about cloud architecture.

The framework has six pillars.

#### 1. Operational Excellence

Focuses on running, monitoring, and continually improving systems and
processes.

Examples: \* Monitor applications and infrastructure using Amazon
CloudWatch. \* Automate operational tasks where appropriate. \* Learn
from operational events and improve procedures. \* Make changes in a
controlled and repeatable way.

#### 2. Security

Focuses on protecting information, systems, and assets while delivering
business value.

Examples: \* Use IAM to manage identities and permissions. \* Apply
least privilege. \* Protect data through appropriate encryption. \*
Record and investigate account activity using AWS CloudTrail. \* Use
security controls at appropriate layers.

#### 3. Reliability

Focuses on the ability of a workload to perform its intended function
correctly and consistently, and to recover from failures.

Examples: \* Distribute resources across multiple Availability Zones
where appropriate. \* Back up important data. \* Test recovery
procedures. \* Avoid single points of failure. \* Monitor workload
health.

#### 4. Performance Efficiency

Focuses on using computing resources efficiently to meet system
requirements and adapting as technologies and demands change.

Examples: \* Select suitable compute and storage resources. \* Monitor
performance and review resource choices. \* Use services such as Auto
Scaling when workloads vary. \* Consider managed services where they
meet workload requirements.

#### 5. Cost Optimization

Focuses on avoiding unnecessary costs and ensuring that spending
delivers business value.

Examples: \* Review cost and usage with AWS Cost Explorer. \* Set
spending thresholds using AWS Budgets. \* Right-size underutilised
resources. \* Select appropriate pricing models. \* Remove resources
that are no longer needed.

#### 6. Sustainability

Focuses on minimising the environmental impacts of running cloud
workloads.

Examples: \* Use resources efficiently. \* Avoid unnecessary idle
capacity. \* Select appropriate managed services and resource
configurations. \* Review workload utilisation and improve efficiency
over time.

**Exam hint:** Learn the purpose of all six pillars and practise
identifying the relevant pillar from a business scenario.

### 3. AWS Global Infrastructure

AWS global infrastructure is organised into Regions, Availability Zones,
and edge locations.

#### AWS Regions

-   A Region is a separate geographical area where AWS operates
    infrastructure.
-   Each Region is designed to be isolated from other Regions.
-   When selecting a Region, consider latency, service availability,
    data residency, compliance, and pricing.
-   Not every AWS service or feature is available in every Region.

#### Availability Zones

-   An Availability Zone consists of one or more discrete data centres
    with independent power, networking, and connectivity.
-   Availability Zones within a Region are connected through
    high-bandwidth, low-latency networking.
-   Deploying resources across multiple Availability Zones can improve
    workload availability and resilience.
-   An Availability Zone belongs to one Region.

#### Edge Locations

-   Edge Locations are sites in the AWS global network.
-   Services such as Amazon CloudFront use edge locations to deliver
    content closer to viewers.
-   Caching content at edge locations can reduce latency and repeated
    requests to an origin.

#### Quick comparison

  Concept             Remember
  ------------------- --------------------------------------------------
  Region              Geographical area
  Availability Zone   Isolated infrastructure location within a Region
  Edge Location       Helps deliver content closer to users

### 4. High Availability and Fault Tolerance

#### High Availability

High Availability (HA) means designing a workload to remain accessible
and operational with minimal downtime.

Typical design approaches: \* Deploy resources across multiple
Availability Zones. \* Use load balancing to distribute traffic across
healthy targets. \* Monitor workload health. \* Plan for recovery when a
component becomes unavailable.

Example: \* An application runs on resources in two Availability Zones.
\* If one Availability Zone has a problem, traffic can be directed to
healthy resources in the other Availability Zone, provided the
application and dependencies are designed for this.

#### Fault Tolerance

Fault tolerance means designing a system to continue operating when one
or more components fail.

Typical design approaches: \* Provide redundancy for critical
components. \* Remove single points of failure. \* Replicate or
distribute data where appropriate. \* Test failure scenarios and
recovery behaviour.

#### Difference

-   High Availability focuses on minimising downtime.
-   Fault Tolerance focuses on continuing operation despite component
    failures.
-   The appropriate design depends on the workload's recovery
    objectives, cost, and business requirements.

### 5. Scalability and Elasticity

#### Scalability

Scalability is the ability to increase or decrease resources to handle
changes in workload.

Two common approaches:

-   **Vertical scaling:** Increase or decrease the capacity of an
    existing resource. For example, change to an EC2 instance type with
    more CPU and memory.
-   **Horizontal scaling:** Add or remove resources. For example, run
    additional EC2 instances behind a load balancer.

#### Elasticity

Elasticity is the ability to adjust resources dynamically as demand
changes.

Example: \* An online shop receives a large increase in traffic during a
sale. \* EC2 Auto Scaling can add instances according to configured
policies. \* When demand decreases, Auto Scaling can reduce the number
of instances.

**Remember:** \* Scalability = Ability to change capacity. \* Elasticity
= Dynamically adjusting capacity as demand changes. \* Auto Scaling = An
AWS capability that can automate capacity adjustments according to
configuration.

### 6. Designing a Secure AWS Architecture

Security is an important part of architecture design. AWS provides
services and controls that help customers secure their workloads.

#### IAM -- Identity and Access Management

-   Controls access to AWS resources.
-   Uses users, groups, roles, and policies.
-   Supports the principle of least privilege.
-   IAM permissions should be reviewed and managed carefully.

#### Security Groups

-   Act as virtual firewalls for supported resources, such as EC2
    instances.
-   Control inbound and outbound traffic.
-   Are stateful: return traffic for an allowed connection is
    automatically permitted.

#### Network ACLs (NACLs)

-   Act as network-level controls for subnets in a VPC.
-   Support allow and deny rules.
-   Are stateless: inbound and outbound traffic are evaluated
    separately.

#### Encryption

-   Helps protect data at rest and in transit.
-   AWS Key Management Service (AWS KMS) helps create and manage
    cryptographic keys.
-   Customers must configure encryption appropriately for their services
    and workloads.

#### Least privilege

-   Give each identity only the permissions needed to perform its tasks.
-   Avoid broad permissions when narrower permissions meet the
    requirement.
-   Review permissions as responsibilities change.

### 7. AWS Shared Responsibility Model

The Shared Responsibility Model explains how security responsibilities
are divided between AWS and its customers.

#### AWS responsibility: Security OF the cloud

AWS is responsible for protecting the infrastructure that runs AWS
services.

Examples include: \* Physical security of data centres. \* Physical
infrastructure and facilities. \* Hardware and foundational networking.
\* Security of the underlying infrastructure used to provide AWS
services.

#### Customer responsibility: Security IN the cloud

Customers are responsible for securing what they run and configure in
AWS. The exact responsibilities depend on the service used.

Examples include: \* Managing IAM users, roles, and permissions. \*
Protecting customer data. \* Configuring network access controls. \*
Managing operating-system and application security where applicable. \*
Configuring encryption and backups according to workload requirements.

#### Example

-   AWS is responsible for physical security of the data centre.
-   The customer is responsible for configuring IAM permissions and
    protecting data stored in its AWS environment.

**Important:** With managed services, AWS may manage more of the
underlying infrastructure. Customer responsibilities still apply to the
data, access, and configuration areas that remain under customer
control.

### 8. Practical example: Online shopping website

A company wants to build an online shopping website using AWS.

  -----------------------------------------------------------------------
  Component               AWS service / concept   Purpose
  ----------------------- ----------------------- -----------------------
  Application hosting     Amazon EC2              Runs the website
                                                  application

  Traffic distribution    Elastic Load Balancing  Distributes incoming
                                                  traffic across targets

  Capacity adjustment     EC2 Auto Scaling        Adds or removes EC2
                                                  capacity according to
                                                  configured policies

  Relational database     Amazon RDS              Stores relational
                                                  application data, such
                                                  as orders

  Object storage          Amazon S3               Stores product images
                                                  and documents

  Access management       AWS IAM                 Controls access to AWS
                                                  resources

  Monitoring              Amazon CloudWatch       Monitors metrics, logs,
                                                  and alarms

  Network isolation       Amazon VPC              Provides a logically
                                                  isolated virtual
                                                  network

  Availability            Multiple Availability   Helps reduce the impact
                          Zones                   of an Availability Zone
                                                  failure
  -----------------------------------------------------------------------

#### Architecture considerations

-   Distribute appropriate resources across multiple Availability Zones.
-   Use a load balancer to route traffic to healthy targets.
-   Configure Auto Scaling based on workload requirements.
-   Keep databases and internal application components in appropriately
    protected network locations.
-   Apply least privilege to identities and workloads.
-   Monitor application health and performance.
-   Review backup, recovery, and cost requirements.

Not every application needs this exact design. Select services and
architecture patterns based on the workload's business, security,
availability, and performance requirements.

### 9. Exam Review -- Practice Questions

These are original practice questions for revision. They are not
official AWS examination questions.

#### Question 1: Cloud computing benefits

A company wants its computing resources to increase when demand rises
and decrease when demand falls automatically. Which concept describes
this?

-   A. High availability
-   B. Elasticity
-   C. Fault tolerance
-   D. Encryption

**Answer: B -- Elasticity.**

Explanation: Elasticity allows resources to adjust dynamically as demand
changes.

#### Question 2: Security

An organisation wants employees to access only the AWS resources
required for their jobs. Which AWS service should it use?

-   A. Amazon CloudWatch
-   B. AWS CloudTrail
-   C. AWS IAM
-   D. Amazon S3

**Answer: C -- AWS IAM.**

Explanation: IAM manages identities and permissions. Least privilege
means granting only the permissions required.

#### Question 3: Storage

A company needs to store images, videos, documents, and backup files as
objects. Which AWS service is most suitable?

-   A. Amazon EC2
-   B. Amazon S3
-   C. Amazon RDS
-   D. Amazon VPC

**Answer: B -- Amazon S3.**

Explanation: Amazon S3 is an object storage service.

#### Question 4: Global infrastructure

A company wants to deploy resources across multiple isolated locations
within the same AWS Region to improve availability. What are these
locations called?

-   A. Edge Locations
-   B. Availability Zones
-   C. AWS Accounts
-   D. CloudFront distributions

**Answer: B -- Availability Zones.**

Explanation: Availability Zones are isolated infrastructure locations
within a Region.

#### Question 5: Monitoring

An administrator wants to monitor EC2 CPU utilisation and receive an
alert when usage becomes too high. Which service should be used?

-   A. AWS CloudTrail
-   B. AWS Cost Explorer
-   C. Amazon CloudWatch
-   D. AWS Budgets

**Answer: C -- Amazon CloudWatch.**

Explanation: CloudWatch collects metrics and supports alarms.

#### Question 6: Account activity

A security team wants to investigate who deleted an EC2 instance and
when the action occurred. Which service should it use?

-   A. Amazon CloudWatch
-   B. AWS CloudTrail
-   C. AWS Trusted Advisor
-   D. AWS Pricing Calculator

**Answer: B -- AWS CloudTrail.**

Explanation: CloudTrail records account activity and API events.

#### Question 7: Cost management

A company wants to analyse AWS spending over the last six months and
identify which services have the highest costs. Which service should it
use?

-   A. AWS Budgets
-   B. AWS Cost Explorer
-   C. AWS CloudTrail
-   D. AWS IAM

**Answer: B -- AWS Cost Explorer.**

Explanation: Cost Explorer analyses historical costs and usage.

#### Question 8: Well-Architected Framework

An organisation wants to reduce unnecessary cloud expenditure and use
AWS resources efficiently. Which Well-Architected pillar addresses this
requirement?

-   A. Security
-   B. Reliability
-   C. Cost Optimization
-   D. Operational Excellence

**Answer: C -- Cost Optimization.**

Explanation: Cost Optimization focuses on avoiding unnecessary costs and
delivering business value.

### 10. Final Exam Memorandum

  Question   Correct answer   Topic
  ---------- ---------------- --------------------
  1          B                Elasticity
  2          C                AWS IAM
  3          B                Amazon S3
  4          B                Availability Zones
  5          C                Amazon CloudWatch
  6          B                AWS CloudTrail
  7          B                AWS Cost Explorer
  8          C                Cost Optimization

**Total: 8 marks**

#### Suggested assessment guide

  Score   Suggested result
  ------- --------------------------------------------------
  7--8    Excellent -- Strong understanding
  5--6    Good -- Review weaker topics
  3--4    Needs improvement -- Revise the relevant lessons
  0--2    Repeat the revision and practise more questions

### 11. Final exam preparation checklist

-   [ ] Explain the six pillars of the AWS Well-Architected Framework.
-   [ ] Distinguish between Regions, Availability Zones, and Edge
    Locations.
-   [ ] Explain High Availability and Fault Tolerance.
-   [ ] Distinguish between Scalability and Elasticity.
-   [ ] Understand vertical and horizontal scaling.
-   [ ] Explain the purpose of EC2 Auto Scaling and Elastic Load
    Balancing.
-   [ ] Understand IAM, Security Groups, NACLs, and encryption.
-   [ ] Explain the AWS Shared Responsibility Model.
-   [ ] Distinguish between CloudWatch and CloudTrail.
-   [ ] Distinguish between Cost Explorer, AWS Budgets, and AWS Pricing
    Calculator.
-   [ ] Practise identifying AWS services from business scenarios.
-   [ ] Review all four CLF-C02 examination domains.

### 12. CLF-C02 examination domain weightings

The AWS Certified Cloud Practitioner CLF-C02 exam guide defines four
domains:

  Domain   Topic                             Weighting
  -------- ------------------------------- -----------
  1        Cloud Concepts                          24%
  2        Security and Compliance                 30%
  3        Cloud Technology and Services           34%
  4        Billing, Pricing, and Support           12%

Use these weightings to guide revision time. The practice questions in
this guide are a short sample and do not represent a full-length
certification examination.

------------------------------------------------------------------------

## Official AWS Learning Resources

-   [AWS Certified Cloud Practitioner -- Exam Guide
    (CLF-C02)](https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/)
-   [AWS Well-Architected
    Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)
-   [AWS Global
    Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/)
-   [AWS Shared Responsibility
    Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
-   [Amazon CloudWatch
    Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)
-   [AWS CloudTrail
    Documentation](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/)
-   [AWS Billing and Cost
    Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)
-   [AWS Support Plans](https://aws.amazon.com/premiumsupport/plans/)
