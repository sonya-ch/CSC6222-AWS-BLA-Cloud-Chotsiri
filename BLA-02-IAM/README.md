# Project: AWS Cloud Practitioner — Biweekly 2 - IAM & AWS Security
# Name: Saranya Chotsiri
# Course: CSC6221 - Database Design 2 
# Instructor: Dr Victor Govindaswamy
# Start Date: 9/14/2026
---

## Overview

This activity is part of my **AWS Cloud Certification Practice Plan**.

In BLA 2, I focused on **AWS Identity and Access Management (IAM)** 
and fundamental AWS security concepts. The goal was to understand how AWS controls access to resources, 
how permissions are evaluated, and how IAM is applied in real-world cloud environments.

The learning activity was divided into three short videos:
1. **IAM Theory** — Understanding IAM fundamentals
2. **How IAM Works** — Understanding authentication, authorization, and policy evaluation
3. **How IAM Is Used** — Applying IAM concepts to a realistic AWS architecture

---

## Purpose of the Activity

* Understand the fundamentals of AWS IAM.
* Learn how AWS manages identities and permissions.
* Understand the difference between IAM Users, Groups, and Roles.
* Understand IAM policies and how AWS evaluates permissions.
* Learn the importance of MFA and Least Privilege.
* Understand how IAM Roles provide temporary credentials.
* Learn how IAM is used to secure AWS workloads.
* Practice explaining AWS security concepts clearly through short educational videos.
* Prepare for AWS Cloud Certification exam questions related to IAM and security.

---

### AWS IAM Components

* IAM Users
* IAM Groups
* IAM Roles
* IAM Policies
* Trust Policies
* Permissions Policies
* Root User
* MFA
* Temporary Credentials

---


# Concepts Learned

## 1. Authentication vs. Authorization

### Authentication

Authentication answers:

> **Who are you?**

It verifies the identity making an AWS request.

### Authorization

Authorization answers:

> **What are you allowed to do?**

It determines whether the identity has permission to perform a specific action on a specific resource.

---

## 2. IAM Users

An IAM User represents a persistent identity within an AWS account.

An IAM User can have credentials and permissions that allow access to AWS resources.

For modern workforce access, AWS recommends using centralized identity and federation approaches such as IAM Identity Center where appropriate.

---

## 3. IAM Groups

An IAM Group is a collection of IAM Users.

Groups make it easier to manage permissions for users with similar responsibilities.

Permissions can be assigned to the group instead of individually configuring every user.

---

## 4. IAM Roles

An IAM Role is an identity that can be assumed to obtain temporary credentials.

A key security benefit is avoiding unnecessary long-term credentials.

---

## 5. IAM Policies

IAM Policies define permissions.

A policy can specify:

* **Effect** — Allow or Deny
* **Action** — What operation can be performed
* **Resource** — Which resource is affected
* **Condition** — Optional conditions under which the permission applies

This represents permission to read objects from a specific S3 bucket.

---

## 6. Explicit Deny

One of the most important IAM concepts learned was:

> **An explicit Deny overrides an Allow.**

This is an important concept for AWS certification exam questions.

---

## 7. Trust Policy vs. Permissions Policy

IAM Roles have an important distinction.

### Trust Policy

Answers:

> **Who can assume this role?**

### Permissions Policy

Answers:

> **What can this role do?**

---

## 8. Multi-Factor Authentication (MFA)

MFA provides an additional authentication factor beyond a password.

Examples include:

* Passkeys
* Security keys
* Authenticator applications

MFA is particularly important for protecting highly privileged identities.

---

## 9. Principle of Least Privilege

Least Privilege means:

> Give an identity only the permissions it actually needs.

For example, if an application only needs to read objects from one S3 bucket, it should not receive full administrator permissions.

---

# Lessons Learned / Reflection

This activity helped me understand that AWS security is not simply about creating users and assigning permissions.

The more important question is:

> **What is the minimum access required for each identity or workload?**

One of my biggest takeaways is the importance of **IAM Roles and temporary credentials** for AWS workloads.

For example, instead of storing long-term credentials inside an EC2 application, the application can use an IAM Role to obtain temporary credentials.

I also learned that IAM policies should be understood logically rather than memorized.

When analyzing an IAM problem, I can ask:

1. Who is making the request?
2. What action are they trying to perform?
3. What resource are they accessing?
4. Is there an applicable Allow?
5. Is there an Explicit Deny?
6. Are the permissions following Least Privilege?

These questions provide a useful framework for solving IAM-related AWS certification questions.

---

# 🎥 YouTube Links

### Video 1 — IAM Theory

🔗 **YouTube:** `Coming Soon`

### Video 2 — How IAM Works

🔗 **YouTube:** `Coming Soon`

### Video 3 — How IAM Is Used

🔗 **YouTube:** `Coming Soon`

---

# LinkedIn Posts

### Video 1 — IAM Theory

🔗 **LinkedIn:** `Coming Soon`

### Video 2 — How IAM Works

🔗 **LinkedIn:** `Coming Soon`

### Video 3 — How IAM Is Used

🔗 **LinkedIn:** `Coming Soon`

---
