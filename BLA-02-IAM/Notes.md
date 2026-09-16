# Project: AWS Cloud Practitioner — Biweekly 2 [Notes]
# Name: Saranya Chotsiri
# Course: CSC6221 - Database Design 2 
# Instructor: Dr Victor Govindaswamy
# Last Update: 9/16/2026

## AWS IAM & Security	IAM, authentication, authorization, security

## Concept Remember
1.	IAM   Controls authentication & authorization
2.	Root User	Full account-level power; avoid for everyday use
3.	IAM User	Persistent identity; use only when appropriate
4.	IAM Group	Collection of IAM users
5.	IAM Role	Assumable identity; temporary credentials
6.	IAM Policy	Defines permissions
7.	Trust Policy	Who can assume a role
8.	Permissions Policy	What the role/user can do
9.	MFA	Adds another authentication factor
10.	Least Privilege	Give only required permissions
11.	Explicit Deny	Overrides an Allow
12.	EC2 + S3	Use IAM Role, not hard-coded access keys
13.	Human workforce	Prefer IAM Identity Center/federation + temporary credentials
14.	Root access keys	Don't create them for normal programmatic access

## FINAL SUMMARY
- IAM helps control:
Who can access AWS resources, what they can do, and under what conditions.
- For people:
Use centralized workforce access where possible.
- For applications:
Use IAM roles instead of hard-coded credentials.
- For permissions:
Follow least privilege.
- For security:
Use MFA, especially for privileged access.
- For the root user:
Protect it, enable MFA, and don't use it for everyday work.
That's the core of how IAM is used in the real world.

