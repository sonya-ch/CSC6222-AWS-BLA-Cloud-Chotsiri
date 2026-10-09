# BLA AWS Cloud — Exam Notes 📝

## AWS Storage & Databases

**Certification:** AWS Certified Cloud Practitioner (CLF-C02)
**Module:** AWS Storage & Databases
**Services:** S3, EFS, RDS, Aurora, DynamoDB
**Purpose:** Quick revision, service comparison, and exam preparation

---

## 1. Quick Memory Sheet

| AWS Service     | Remember       | Primary Use                                                        |
| --------------- | -------------- | ------------------------------------------------------------------ |
| Amazon S3       | Object         | Store objects such as images, videos, and backups                  |
| Amazon EFS      | File           | Shared file system for multiple compute resources                  |
| Amazon RDS      | Relational     | Managed relational databases                                       |
| Amazon Aurora   | AWS Relational | AWS-built relational database compatible with MySQL and PostgreSQL |
| Amazon DynamoDB | NoSQL          | Managed key-value and document database                            |

### Five Keywords to Remember

* **S3 = Object Storage**
* **EFS = Shared File Storage**
* **RDS = Relational Database**
* **Aurora = AWS-Built Relational Database**
* **DynamoDB = NoSQL Database**

---

## 2. Amazon S3 — Simple Storage Service

**Type:** Object storage

### Key Concepts

* Stores data as objects inside buckets.
* Suitable for images, videos, documents, backups, logs, and data files.
* Designed for high durability.
* Offers storage classes for different access patterns and cost requirements.
* Supports lifecycle policies to transition or expire objects automatically.

### Exam Keywords

`Object storage` · `Buckets` · `Images` · `Backups` · `Data files`

### Remember

If the requirement is to store large amounts of unstructured data as objects, consider **Amazon S3**.

**Common confusion:** S3 is not the same as a shared network file system.

---

## 3. Amazon EFS — Elastic File System

**Type:** Managed file storage

### Key Concepts

* Provides a shared file system.
* Multiple supported compute resources can access the same file system.
* Commonly used with Linux-based workloads on Amazon EC2.
* Automatically grows and shrinks as files are added and removed, subject to the selected configuration and service behavior.

### Exam Keywords

`Shared file system` · `Multiple EC2 instances` · `File storage`

### Remember

If multiple servers need to access the same shared file system, consider **Amazon EFS**.

**Common confusion:** EFS provides file system access, while S3 stores objects.

---

## 4. Amazon RDS — Relational Database Service

**Type:** Managed relational database service

### Key Concepts

* Uses relational database engines.
* Supports SQL-based workloads.
* Organizes structured data into tables, rows, and columns.
* AWS manages many administrative tasks.
* Supports automated backups and other managed database capabilities.

### Supported Database Engines

* MySQL
* PostgreSQL
* MariaDB
* Oracle
* Microsoft SQL Server
* Amazon Aurora

### Exam Keywords

`Relational database` · `SQL` · `Managed database` · `Structured data`

### Remember

If an application needs a managed relational database, consider **Amazon RDS**.

**Common confusion:** RDS is a managed database service, not a NoSQL database.

---

## 5. Amazon Aurora

**Type:** AWS-built relational database

### Key Concepts

* Compatible with MySQL and PostgreSQL.
* Designed for high performance and availability.
* Provides managed relational database capabilities.
* Available as an engine within the Amazon RDS service.

### Exam Keywords

`AWS-built database` · `MySQL-compatible` · `PostgreSQL-compatible` · `Relational`

### Remember

If the requirement specifically calls for an AWS-built relational database compatible with MySQL or PostgreSQL, consider **Amazon Aurora**.

**Common confusion:** Aurora is part of the RDS family of managed database offerings. It is not a NoSQL database.

---

## 6. Amazon DynamoDB

**Type:** Managed NoSQL database

### Key Concepts

* Supports key-value and document data models.
* Is fully managed and serverless.
* Designed for scalable workloads and low-latency data access.
* Commonly used for gaming applications, shopping carts, user sessions, and other application data.

### Exam Keywords

`NoSQL` · `Key-value` · `Document database` · `Serverless` · `Low latency` · `Scalability`

### Remember

If the requirement calls for a highly scalable, managed NoSQL database, consider **Amazon DynamoDB**.

**Common confusion:** DynamoDB is not a traditional relational SQL database.

---

## 7. Service Comparison — Exam Decision Table

| Requirement                                                              | Service to Consider |
| ------------------------------------------------------------------------ | ------------------- |
| Store images and videos as objects                                       | Amazon S3           |
| Store backups and data files as objects                                  | Amazon S3           |
| Provide a shared file system                                             | Amazon EFS          |
| Run a managed MySQL database                                             | Amazon RDS          |
| Run a managed relational database using PostgreSQL                       | Amazon RDS          |
| Use an AWS-built relational database compatible with MySQL or PostgreSQL | Amazon Aurora       |
| Build a scalable NoSQL application                                       | Amazon DynamoDB     |
| Store shopping cart data using a NoSQL data model                        | Amazon DynamoDB     |

**Exam tip:** The correct answer depends on the complete requirements. For example, both RDS and Aurora can support relational workloads, so look for the specific database engine, performance, availability, and compatibility requirements in the question.

---

## 8. Common Exam Traps

### Trap 1 — S3 vs. EFS

* Object storage → S3
* Shared file system → EFS

Do not choose S3 simply because a question mentions files. Identify how the application needs to store and access them.

### Trap 2 — RDS vs. DynamoDB

* Relational SQL database → RDS or Aurora
* NoSQL key-value/document database → DynamoDB

### Trap 3 — RDS vs. Aurora

* General managed relational database requirement → RDS may be appropriate.
* AWS-built relational engine compatible with MySQL or PostgreSQL → Aurora may be appropriate.

### Trap 4 — Serverless Does Not Mean No Servers Exist

DynamoDB is serverless from the customer's management perspective. AWS still operates the underlying infrastructure.

### Trap 5 — One Application Can Use Multiple Services

An e-commerce application could use:

* S3 for product images
* RDS or Aurora for relational customer and order data
* DynamoDB for a shopping cart that benefits from a NoSQL data model

Choose each service according to the specific workload.

---

## 9. Exam Practice Questions

Try answering each question before revealing the answer.

### Question 1

A company needs to store millions of product images for an online store. Which service is most appropriate?

A. Amazon RDS
B. Amazon EFS
C. Amazon S3
D. Amazon DynamoDB

<details>
<summary>Show answer and explanation</summary>

**Answer: C — Amazon S3**

S3 is object storage designed for data such as images, videos, and backups.

</details>

### Question 2

Multiple EC2 instances need to access a shared file system. Which service should the company consider?

A. Amazon S3
B. Amazon EFS
C. Amazon DynamoDB
D. Amazon Aurora

<details>
<summary>Show answer and explanation</summary>

**Answer: B — Amazon EFS**

EFS provides a shared file system that supported compute resources can access.

</details>

### Question 3

A company wants a managed relational database that supports MySQL. Which service is appropriate?

A. Amazon DynamoDB
B. Amazon S3
C. Amazon RDS
D. Amazon EFS

<details>
<summary>Show answer and explanation</summary>

**Answer: C — Amazon RDS**

RDS supports MySQL and provides managed relational database capabilities. Aurora is another MySQL-compatible option when its specific features meet the requirements.

</details>

### Question 4

A company wants an AWS-built relational database compatible with PostgreSQL. Which service should it consider?

A. Amazon S3
B. Amazon Aurora
C. Amazon EFS
D. Amazon DynamoDB

<details>
<summary>Show answer and explanation</summary>

**Answer: B — Amazon Aurora**

Aurora is an AWS-built relational database compatible with PostgreSQL and MySQL.

</details>

### Question 5

A mobile application requires a scalable NoSQL database with low-latency access. Which service is the best fit?

A. Amazon RDS
B. Amazon EFS
C. Amazon DynamoDB
D. Amazon S3

<details>
<summary>Show answer and explanation</summary>

**Answer: C — Amazon DynamoDB**

DynamoDB is a managed NoSQL database designed for scalable workloads and low-latency access.

</details>

---

## 10. Final Revision Checklist

Before the exam, make sure you can explain these concepts without looking at your notes.

* [ ] I can explain object storage and identify Amazon S3.
* [ ] I can explain a shared file system and identify Amazon EFS.
* [ ] I can distinguish relational databases from NoSQL databases.
* [ ] I can identify common database engines supported by RDS.
* [ ] I understand Aurora's compatibility with MySQL and PostgreSQL.
* [ ] I can explain DynamoDB's key-value and document data models.
* [ ] I can choose services based on a business scenario.
* [ ] I can explain why an option is correct and why the alternatives are less appropriate.

---

## 11. Official Study Resources

Use these resources to validate your understanding and review current service capabilities.

* [AWS Certified Cloud Practitioner — Official Exam Page](https://aws.amazon.com/certification/certified-cloud-practitioner/)
* [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
* [Amazon EFS Documentation](https://docs.aws.amazon.com/efs/)
* [Amazon RDS Documentation](https://docs.aws.amazon.com/rds/)
* [Amazon Aurora Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/)
* [Amazon DynamoDB Documentation](https://docs.aws.amazon.com/dynamodb/)

---

## Final Memory Trick

> **S3 = Objects**
> **EFS = Shared Files**
> **RDS = Relational Database**
> **Aurora = AWS-Built Relational Database**
> **DynamoDB = NoSQL Database**

**Exam strategy:** Identify the requirement → recognize the key concept → select the appropriate AWS service → verify that it meets the complete scenario.

*These notes are a study aid, not a substitute for the current official exam guide. Practice questions in this file are original and are not official AWS exam questions.*
