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

---

# 🛠️ AWS Scenario-Based Interview Q&A — Revision Notes

---

## 11. How would you secure an application using IAM roles and policies?

I would follow the principle of least privilege, creating IAM policies that grant only required permissions. Then I'd attach them to IAM roles instead of users, allowing services like EC2 or Lambda to securely access AWS resources. I'd also enable MFA and use temporary credentials via roles for better security.

---

## 12. Your S3 bucket is accidentally made public. How would you fix and prevent this?

First, I would immediately block public access at the bucket level and remove any public policies or ACLs. Then I'd enable S3 Block Public Access and use bucket policies with least privilege. To prevent future issues, I'd enable AWS Config rules and CloudTrail alerts for public access detection.

---

## 13. How would you monitor and troubleshoot an application using CloudWatch?

I would use CloudWatch metrics and dashboards to monitor CPU, memory, and latency. Then I'd enable CloudWatch Logs to analyze application logs and set alarms for anomalies. For troubleshooting, I'd correlate logs with metrics and use CloudWatch Insights for deeper analysis.

---

## 14. You want zero downtime deployment. How would you achieve this in AWS?

I would use Blue-Green deployment or Rolling updates with services like Auto Scaling and Load Balancer. Traffic would gradually shift to the new version while keeping the old version active. This ensures no downtime and allows quick rollback if issues occur.

---

## 15. How would you design a multi-tier architecture (frontend, backend, database) on AWS?

I'd use ALB + EC2/Lambda for the frontend layer, backend services in private subnets, and a database like RDS in a private subnet. Security groups would restrict access between tiers. I'd also use Auto Scaling and load balancing for high availability.

---

## 16. Your application needs to serve millions of users globally. How would you architect it?

I would use CloudFront CDN for global content delivery and Route 53 latency-based routing. Backend services would run on Auto Scaling groups across multiple regions. I'd also use caching (ElastiCache) and database replication for performance and scalability.

---

## 17. How would you migrate an on-premise application to AWS with minimal downtime?

I would use a lift-and-shift (rehost) strategy using AWS Application Migration Service or DMS for databases. Data would be replicated continuously until cutover. Then I'd switch traffic using DNS with minimal downtime.

---

## 18. You need to restrict access between services within a VPC. How would you implement this?

I would use Security Groups for instance-level control and NACLs for subnet-level restrictions. Only required ports and IP ranges would be allowed between services. Additionally, I'd use private subnets and avoid exposing internal services to the internet.

---

## 19. Your application is slow due to database bottlenecks. How would you optimize performance?

I would add read replicas to offload read traffic and use caching (Redis/ElastiCache). I'd also optimize queries, add indexing, and consider scaling vertically or horizontally. Monitoring with CloudWatch would help identify exact bottlenecks.

---

## 20. How would you design a disaster recovery (DR) strategy in AWS?

I would choose a strategy based on RTO/RPO like backup & restore, pilot light, warm standby, or multi-region active-active. Data would be replicated across regions using services like S3 replication or RDS snapshots. Regular DR drills and automation ensure quick recovery.
