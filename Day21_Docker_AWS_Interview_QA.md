# 🚀 Day 21 of 30 – DevOps Interview Preparation Challenge
## 25 Docker & AWS Interview Questions with Detailed Answers

### 🌟 Introduction
If you’re preparing for a **DevOps Engineer interview**, two areas you will always be tested on are:  
1. **Docker** – because containerization is at the core of modern DevOps.  
2. **AWS** – because it is the most widely adopted cloud provider.  

This document covers **25 commonly asked Docker and AWS questions** with detailed answers, designed to strengthen your theory and practical preparation.

---

## 🐳 Docker Interview Questions

### Q1: What is Docker?
Docker is a **containerization platform** that packages applications and dependencies together into a lightweight, portable container.  
It ensures the app runs consistently across environments, eliminating the “works on my machine” problem.

---

### Q2: What is the difference between Docker containers and Virtual Machines?
- **Virtual Machines (VMs)** → Require a hypervisor, each VM runs a full OS, making them **heavier** and slower to boot.  
- **Docker Containers** → Share the host OS kernel, are **lightweight**, and start within seconds.  

**Key Point:** Containers are more efficient for microservices architectures.

---

### Q3: Difference between Docker Image and Container?
- **Image** → Immutable blueprint for creating containers (read-only).  
- **Container** → Running instance of an image (read-write).  

Think of **Image = Class** and **Container = Object**.

---

### Q4: How do you persist data in Docker?
By using:  
- **Volumes** → Managed by Docker, recommended for persistence.  
- **Bind Mounts** → Link host directories to containers.  

**Example:**  
```bash
docker run -v myvolume:/app/data myimage
```

---

### Q5: What are common instructions in a Dockerfile?
- `FROM` → Defines the base image  
- `COPY`/`ADD` → Copy files into the image  
- `RUN` → Execute commands while building  
- `EXPOSE` → Defines ports to be exposed  
- `CMD` → Default command when container runs  

---

### Q6: What is Docker Compose?
A tool to define and run **multi-container applications** with a YAML file (`docker-compose.yml`).  

**Example:**  
```yaml
version: '3'
services:
  web:
    image: nginx
  db:
    image: mysql
```

---

### Q7: How do you reduce Docker image size?
- Use **smaller base images** (e.g., `alpine`)  
- Use **multi-stage builds**  
- Remove caches and unnecessary packages  

---

### Q8: Difference between `COPY` and `ADD` in Dockerfile?
- `COPY` → Copies files/folders only.  
- `ADD` → Can also extract tar archives and fetch remote URLs.  

Best practice → Use `COPY` unless `ADD` features are needed.

---

### Q9: How do you monitor Docker containers?
- CLI commands: `docker ps`, `docker stats`  
- Tools: **Prometheus + cAdvisor**, **ELK Stack**, Docker Desktop dashboard  

---

### Q10: What is the difference between ENTRYPOINT and CMD?
- `ENTRYPOINT` → Defines the main executable (cannot be overridden easily).  
- `CMD` → Provides default arguments to ENTRYPOINT.  

**Example:**  
```dockerfile
ENTRYPOINT ["python3", "app.py"]
CMD ["--debug"]
```

---

## ☁️ AWS Interview Questions

### Q11: What is IAM in AWS?
IAM (**Identity and Access Management**) is a service to securely manage **users, groups, roles, and permissions**.  
It uses **policies (JSON documents)** to define access.

---

### Q12: Difference between Security Groups and NACLs?
- **Security Groups** → Instance-level firewall, stateful (return traffic automatically allowed).  
- **NACLs** → Subnet-level firewall, stateless (rules must be defined for inbound & outbound separately).  

---

### Q13: How do you achieve high availability with EC2?
- Deploy across **multiple Availability Zones**  
- Use **Auto Scaling Groups**  
- Add **Elastic Load Balancer (ELB/ALB)**  

---

### Q14: What is the difference between S3 Standard and S3 Glacier?
- **S3 Standard** → Low-latency, frequent access storage.  
- **S3 Glacier** → Archival storage, very cheap, retrieval takes minutes to hours.  

---

### Q15: Explain Spot, Reserved, and On-Demand EC2 instances.
- **On-Demand** → Flexible, pay per use.  
- **Reserved** → Cheaper with 1–3 year commitment.  
- **Spot** → Very cheap but can be terminated anytime.  

---

### Q16: What is AWS CloudFormation?
An **Infrastructure as Code (IaC)** tool that provisions AWS resources using YAML/JSON templates.  
Useful for automation and reproducibility.

---

### Q17: Difference between Elastic Beanstalk and ECS?
- **Elastic Beanstalk** → PaaS for easy app deployment, abstracts infrastructure.  
- **ECS (Elastic Container Service)** → Orchestrates Docker containers, gives more control.  

---

### Q18: What is AWS EKS?
EKS (**Elastic Kubernetes Service**) is AWS’s **managed Kubernetes** service, reducing the operational overhead of running K8s clusters.

---

### Q19: How do you secure sensitive data in AWS?
- Use **Secrets Manager**  
- Use **SSM Parameter Store**  
Avoid hardcoding credentials in applications.

---

### Q20: Difference between ELB and ALB?
- **ELB (Classic Load Balancer)** → Layer 4 & 7, older generation.  
- **ALB (Application Load Balancer)** → Layer 7, supports path-based & host-based routing (ideal for microservices).  

---

### Q21: How do you connect on-premises servers to AWS?
Options include:  
- **VPN connection**  
- **AWS Direct Connect** (dedicated line)  
- Hybrid networking solutions  

---

### Q22: Difference between RDS and DynamoDB?
- **RDS** → Relational, SQL-based (e.g., MySQL, PostgreSQL).  
- **DynamoDB** → NoSQL, key-value/document based.  

---

### Q23: What is AWS Lambda used for?
Serverless compute service – runs code without provisioning servers.  
Triggered by events (e.g., S3 upload, API Gateway, CloudWatch event).  

---

### Q24: How do you manage logs in AWS?
- **CloudWatch Logs**  
- Store in **S3**  
- Analyze using **Athena** or **OpenSearch**  

---

### Q25: What is an Auto Scaling Policy?
Rules that automatically **scale EC2 instances** based on metrics like CPU usage, memory, or custom CloudWatch alarms.

---

## 🎯 Interview Preparation Tips
- Don’t just **memorize** – practice hands-on using **Docker** and **AWS Free Tier**.  
- Expect **scenario-based questions** (e.g., “How would you deploy a web app with HA?”).  
- Use the **STAR Method** (Situation, Task, Action, Result) for real-world answers.  
- Stay updated with official documentation, as services evolve quickly.

---

## 🏁 Conclusion
We covered **25 Docker & AWS questions with detailed answers**.  
This knowledge strengthens your interview preparation and hands-on skills.  

💡 Tip: Deploy a small app using **Docker + AWS EC2 + S3** to stand out in interviews.

---

#DevOps #Docker #AWS #InterviewPreparation #30DaysOfDevOps #Cloud
