# Project: AWS Cloud Practitioner - Compute Services
# Name: Saranya Chotsiri
# Course: CSC6221 - Database Design 2
# Instructor: Dr Victor Govindaswamy
# Start Date: 9/22/2026

## Overview
This biweekly project explores AWS Compute Services and how they are used to run applications, manage computing resources, and support scalable cloud architectures.

## Learning Objectives
- Understand the fundamentals of AWS Compute Services.
- Learn the differences between EC2, EBS, AMI, ELB, Auto Scaling, and Lambda.
- Understand how compute services work together.
- Explore a real-world example using an online food ordering application.

## Key Concepts
| AWS Service | Description |
|---|---|
| **EC2** | Virtual servers for running applications. |
| **EBS** | Persistent block storage for EC2 instances. |
| **AMI** | Template used to launch EC2 instances. |
| **ELB** | Distributes incoming traffic across servers. |
| **Auto Scaling** | Automatically adjusts the number of EC2 instances. |
| **Lambda** | Runs code in response to events without managing servers. |

## How It Works
A typical application architecture can use:

**Users → Load Balancer → EC2 Instances → Application**
- **ELB:** Distributes incoming requests.
- **Auto Scaling:** Adds or removes EC2 instances based on demand.
- **EBS:** Provides persistent storage.
- **AMI:** Helps launch instances with consistent configurations.
- **Lambda:** Executes event-driven tasks.

## Real-World Example

### Online Food Ordering Application

AWS Compute Services can support an online food ordering application:
- **EC2:** Runs the backend application and APIs.
- **ELB:** Distributes customer requests across EC2 instances.
- **Auto Scaling:** Handles increased traffic during busy hours.
- **EBS:** Stores application and operating system data.
- **AMI:** Provides a reusable template for new instances.
- **Lambda:** Processes food images or other event-driven tasks.

## Exam Key Takeaways
- **EC2 vs Lambda:** EC2 provides virtual servers; Lambda runs code without requiring us to manage servers.
- **AMI vs EBS:** AMI is an instance template; EBS is persistent storage.
- **ELB vs Auto Scaling:** ELB distributes traffic; Auto Scaling adjusts the number of instances.

## YouTube Video Overview
1. **Theory:** Introduction to AWS Compute Services and their main concepts. https://youtu.be/DumL7DTuBeg
2. **How It Works:** Explanation of how EC2, ELB, Auto Scaling, EBS, AMI, and Lambda work together. https://youtu.be/FWAvX7jiRn0
3. **Real-World Example:** Applying AWS Compute Services to an online food ordering application. https://youtu.be/cvYkN6hohNU

## LinkedIn Posts
1. https://www.linkedin.com/feed/update/urn:li:activity:7510548333363396609/
2. https://www.linkedin.com/feed/update/urn:li:activity:7510548808221650944/
3. https://www.linkedin.com/feed/update/urn:li:activity:7510549290289700865/

## Conclusion
AWS Compute Services provide flexible options for running applications, managing resources, and supporting scalable cloud solutions. Understanding these services helps developers design applications based on different workloads and requirements.
