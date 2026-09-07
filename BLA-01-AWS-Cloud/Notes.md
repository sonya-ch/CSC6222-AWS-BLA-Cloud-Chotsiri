# Project: AWS Cloud Practitioner — Biweekly 1 [Notes]
# Name: Saranya Chotsiri
# Course: CSC6221 - Database Design 2 
# Instructor: Dr Victor Govindaswamy

## 1. Cloud Computing

### What is Cloud Computing?

Cloud computing is the on-demand delivery of computing resources over the internet.

Examples of cloud resources include:
* Compute
* Storage
* Databases
* Networking
* Security
* Machine Learning

Instead of purchasing and maintaining physical infrastructure, organizations can use resources provided by a cloud provider.

### On-Premises vs. Cloud
-----------------------------------------------------------------------------------
| On-Premises                    | Cloud                                          |
| ------------------------------ | ---------------------------------------------- |
| Buy physical hardware          | Rent cloud resources                           |
| Large upfront cost             | Pay-as-you-go                                  |
| Manage physical infrastructure | Cloud provider manages physical infrastructure |
| Scaling can take time          | Resources can be scaled more easily            |
| Limited physical capacity      | Flexible capacity                              |
-----------------------------------------------------------------------------------

### Benefits of Cloud Computing

* **On-demand:** Resources can be provisioned when needed.
* **Pay-as-you-go:** Pay based on usage.
* **Scalability:** Increase or decrease resources based on demand.
* **Global reach:** Deploy applications in different geographic locations.
* **Reduced infrastructure management:** The cloud provider manages the underlying physical infrastructure.

---


## 2. Cloud Service Models

### IaaS — Infrastructure as a Service
Provides basic computing infrastructure such as:
* Virtual machines
* Storage
* Networking
The customer has more control but also more responsibility.

**Example:** Amazon EC2

### PaaS — Platform as a Service
The cloud provider manages more of the underlying infrastructure, allowing developers to focus more on their applications.

### SaaS — Software as a Service
The customer uses a complete software application without managing the underlying infrastructure.

**Examples:**
* Gmail
* Microsoft 365

### Easy Way to Remember

**IaaS → Infrastructure**

**PaaS → Platform**

**SaaS → Software**

As we move from IaaS → PaaS → SaaS, the cloud provider manages more of the underlying infrastructure.

---

# 3. Introduction to AWS

## What is AWS?
AWS stands for **Amazon Web Services**.

AWS is a cloud computing platform that provides many different services for building, deploying, and managing applications.

AWS services can be grouped into different categories.


### Common AWS Services
-------------------------------------------------------------
| Category   | AWS Service | Purpose                        |
| ---------- | ----------- | ------------------------------ |
| Compute    | EC2         | Virtual servers                |
| Storage    | S3          | Object storage                 |
| Database   | RDS         | Relational databases           |
| Database   | DynamoDB    | NoSQL database                 |
| Networking | VPC         | Virtual networking             |
| Security   | IAM         | Identity and access management |
-------------------------------------------------------------

### Important Concept
AWS is **not one service**.
It is a collection of many cloud services that can work together.

For example, an application might use:
**EC2 → Run the application**
**S3 → Store files**
**RDS → Store relational data**
**IAM → Control access**
**VPC → Provide networking**

---

# 4. AWS Global Infrastructure

## AWS Region
An AWS Region is a geographic area containing multiple Availability Zones.

Examples include regions in:
* North America
* Europe
* Asia Pacific


### Why Choose a Region?

Important considerations include:
* Latency
* Data residency
* Compliance
* Service availability
* Pricing

---


## Availability Zone

An Availability Zone (AZ) consists of one or more discrete data centers within an AWS Region.
A Region contains multiple Availability Zones.
Availability Zones are designed to be isolated from failures in other Availability Zones.


### Why Use Multiple AZs?
Using multiple Availability Zones can improve **high availability**.


For example:

AWS Region
 * Availability Zone A
    - Application Server
 * Availability Zone B
    - Application Server
If one Availability Zone has a problem, resources in another Availability Zone may continue operating.

---


# 5. Edge Locations

Edge Locations are locations used by AWS services such as Amazon CloudFront to deliver content closer to users.

For example:

User
  ↓
Nearest Edge Location
  ↓
AWS Region


Content such as images, videos, CSS, and JavaScript files can be cached closer to users.
This can help reduce latency and improve performance.

---


# 6. Region vs. Availability Zone vs. Edge Location
------------------------------------------------------------------------
| Concept           | Meaning                                          |
| ----------------- | ------------------------------------------------ |
| Region            | Geographic area containing AWS infrastructure    |
| Availability Zone | Isolated location within a Region                |
| Edge Location     | Location used to deliver content closer to users |
------------------------------------------------------------------------

### Easy Way to Remember

**Region = Geographic area**
**AZ = Data center area inside a Region**
**Edge Location = Closer to the user**

---


# 7. Key Exam Concepts

### Scalability
The ability to increase or decrease resources based on demand.

### High Availability
Designing systems to remain available even when some components fail.

### Pay-as-you-go
Pay for the resources you actually use.

### IaaS
Infrastructure as a Service.

### PaaS
Platform as a Service.

### SaaS
Software as a Service.

### Region
A geographic area containing multiple Availability Zones.

### Availability Zone
One or more discrete data centers within a Region.

### Edge Location
A location used by services such as CloudFront to deliver content closer to users.


---

# 8. Key Takeaways

1. Cloud computing provides computing resources over the internet.
2. Cloud computing can reduce the need to purchase physical infrastructure.
3. IaaS, PaaS, and SaaS represent different levels of cloud service management.
4. AWS provides many different cloud services.
5. AWS Regions contain multiple Availability Zones.
6. Multiple Availability Zones can help improve availability.
7. Edge Locations help deliver content closer to users.

---
