# 🎯 Interview Revision — Nakul Surve

---

## Q1. Tell me about yourself and walk me through your background.

Hi, my name is Nakul Surve, and I’m a self-taught Cloud and DevOps engineer based in Pune.

I started my career as a professional pastry chef, but I wanted to move into IT. I became interested in cloud and DevOps, so I started learning AWS, Docker, and Kubernetes.and I’ve worked on deploying applications using CI/CD pipelines. I’m also AWS Solutions Architect certified.

Currently, I’m looking for an opportunity to start my career in DevOps and grow my skills in a real-world environment

---

## "Why DevOps / Cloud?

I chose DevOps because it focuses on automation, scalability, and real-world system management. I like the idea of building systems that can deploy and run applications efficiently.

Cloud platforms like AWS make it possible to build and scale applications easily, and DevOps tools like Docker and Kubernetes make deployments faster and more reliable.

This combination of development, operations, and automation is what attracted me to this field.

---

## Q3. Walk me through one AWS project you've built. What did you architect and what problems did you hit?

**A:** “I built a project called HBO-Stream, a cost-optimized video streaming platform on AWS. I used a VPC with public and private subnets across two AZs. An ALB handles traffic, and the app runs on EC2 using Docker Compose. I used RDS PostgreSQL for database, S3 for storage, and CloudFront for fast delivery. Everything was provisioned using Terraform with S3 backend and DynamoDB locking.
        I faced issues like ALB requiring multiple AZs and CIDR conflicts, which I solved by redesigning the architecture.”
---

## Q4. Where do you see yourself in 2 years? Why SRE specifically?

**A:** Honest roadmap: in 6–12 months, I want to be a contributing Junior DevOps engineer — writing Terraform, managing CI/CD pipelines, supporting infrastructure, participating in on-call rotations. In year two, I want to have developed enough observability and incident response skills to operate closer to an SRE function. Why SRE? Because it combines engineering rigour with operational reliability — and it's driven by data. The error budget model — define an SLO, measure burn rate, make decisions based on reliability math — that's the thinking I want to be doing. I've read the Google SRE book. I understand toil, post-mortems, and the difference between reactive ops and proactive reliability engineering. I'm not trying to shortcut to SRE. I want to earn it. I'm asking for a junior role because that's where I genuinely am — I'd rather be honest than oversell and underdeliver.

---

## "What is your greatest strength?"

**A:** My biggest strength is troubleshooting and persistence. In DevOps, things rarely work the first time. For example, when setting up my HBO-Stream infrastructure, I ran into several CIDR block conflicts. I didn't stop until I understood the networking logic behind it and fixed the Terraform code.

---

## "Why should we hire you without a CS degree?"

**A:** While I don't have a formal degree, I have spent the last year treating my self-study like a full-time job. I've built actual infrastructure from scratch, passed professional-grade certifications, and I'm highly adaptable. I'm not just here because of a degree; I'm here because I actually love building and automating systems.

---

## "How do you handle a situation where you don't know the answer?"

**A:** First, I check the official documentation — like the HashiCorp docs for Terraform. If that doesn't solve it, I use community resources like StackOverflow or GitHub issues. If I'm still stuck after 30 minutes of deep-diving, I'll reach out to a senior or a peer with a clear summary of what I've already tried.

---

