# ☁️ AWS Interview Q&A — Revision Notes

---

## 1. What is the difference between EC2 and Lambda?

EC2 provides virtual servers where you manage OS, scaling, and runtime. Lambda is serverless, where you just upload code and AWS automatically handles execution and scaling. EC2 is best for long-running apps, while Lambda is ideal for event-driven workloads.

---

## 2. Explain different types of EBS volumes and their use cases

EBS volumes include gp2/gp3 (general purpose) for balanced performance, io1/io2 (provisioned IOPS) for high-performance databases, and st1/sc1 (HDD) for throughput-heavy or archival workloads. gp3 is most commonly used due to cost efficiency and flexibility. io volumes are used when low latency and high IOPS are critical.

---

## 3. What is the difference between S3 storage classes?

S3 offers classes like Standard (frequent access), Standard-IA (infrequent access), Glacier (archival), and Intelligent-Tiering. They differ in cost, retrieval time, and availability. Choosing the right class helps optimize storage cost based on access patterns.

---

## 4. How does Auto Scaling work in AWS?

Auto Scaling automatically adjusts the number of EC2 instances based on demand using scaling policies. It uses metrics like CPU or request count to scale out (add instances) or scale in (remove instances). This ensures high availability and cost optimization.

---

## 5. What is the difference between Application Load Balancer and Network Load Balancer?

ALB (Layer 7) works at HTTP/HTTPS level and supports routing based on path, host, and headers. NLB (Layer 4) works at TCP/UDP level and provides ultra-low latency and high performance. ALB is best for web apps, while NLB is used for high-throughput or real-time systems.

---

## 6. What is a VPC and its key components?

A VPC (Virtual Private Cloud) is a logically isolated network in AWS where you launch resources. Key components include subnets, route tables, internet gateway, NAT gateway, and security groups. It gives you full control over networking and security.

---

## 7. Explain the difference between public subnet and private subnet

A public subnet has a route to an Internet Gateway, allowing resources to access the internet. A private subnet does not have direct internet access. Private subnets are used for databases and backend services for better security.

---

## 8. What is a NAT Gateway and why is it used?

A NAT Gateway allows instances in a private subnet to access the internet without exposing them publicly. It is mainly used for downloading updates or external API calls. It improves security by preventing inbound internet traffic.

---

## 9. What is the difference between IAM roles and policies?

IAM policies are JSON documents that define permissions (what actions are allowed or denied). IAM roles are entities that you assign these policies to and can be assumed by users, services, or applications. Roles provide temporary credentials and better security.

---

## 10. How does CloudWatch work?

CloudWatch collects metrics, logs, and events from AWS resources. It allows you to monitor performance, set alarms, and trigger automated actions. It is essential for observability and troubleshooting in AWS.
