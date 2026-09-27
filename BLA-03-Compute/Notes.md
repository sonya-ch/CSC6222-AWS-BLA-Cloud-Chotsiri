# Notes : BLA3 - Compute

- EC2 provides virtual servers.
- EBS provides persistent storage for EC2.
- AMI provides a template for launching EC2 instances.
- ELB distributes traffic across multiple servers.
- Auto Scaling automatically adjusts the number of servers based on demand.
- Lambda allows us to run code without managing servers.
These services give developers different options for building scalable and reliable applications in the AWS cloud.

---

## What is Compute?
- EC2 = Server
- EBS = Hard drive
- AMI = Server template
- ELB = Traffic distributor
- Auto Scaling = Add/remove servers
- Lambda = Run code without managing servers
---

## HOW it works?
User → Load Balancer → EC2
↓
Auto Scaling adds/removes EC2
↓
EBS = storage
- AMI = template
- Lambda = event → function

---

## REAL WORLD - Food App
- EC2 = Backend
- EBS = Storage
- ELB = Users → Servers
- Auto Scaling = Lunch/dinner traffic
- AMI = Copy server setup
- Lambda = Process uploaded food image

---

## Exam Keys
### Service:
- EC2	🖥️ Virtual Server
- EBS	💾 Persistent Storage
- AMI	📦 Instance Template
- ELB	🚦 Distribute Traffic
- Auto Scaling	📈 Adjust Instances
- Lambda	⚡ Run Code / Serverless

---

## What difference? 
-	EC2 vs Lambda → EC2 = We manage server | Lambda = AWS manages server
-	AMI vs EBS → AMI = template to create instance | EBS = storage
-	ELB vs Auto Scaling → ELB = spread traffic | Auto Scaling = De/increase instances

