# 🚀 Day 14 of 30 Days DevOps Interview Preparation

## 📌 Today's Agenda
- Revise **Week 2** concepts (Git, CI/CD, Docker, Jenkins, GitHub Actions).
- Cover **20 CI/CD Interview Questions** with detailed answers.
- Add **theory + AWS practical insights**.

---

## 🔄 Week 2 Revision Topics
- **Git & Version Control**: Branching strategies, Git workflows, rollback strategies.
- **CI/CD Fundamentals**: Continuous Integration, Continuous Delivery, Continuous Deployment.
- **Docker**: Containerization basics, Dockerfile, Docker Hub, ECR integration.
- **Jenkins**: Declarative pipelines, plugins, agents, jobs.
- **GitHub Actions**: YAML workflows, secrets, runners, integration with AWS.
- **AWS for DevOps**: EC2, S3, IAM, CloudWatch basics for pipeline integration.

---

## ❓ 20 CI/CD Interview Questions with Detailed Answers

### 1. What is CI/CD?
**Answer:**  
- **Continuous Integration (CI):** Developers frequently merge code into a shared repo → automated builds/tests ensure early bug detection.  
- **Continuous Delivery (CD):** Code is always in a deployable state. Automated testing + packaging ensures smooth delivery.  
- **Continuous Deployment:** Extends CD → automatically deploys to production without manual approval.

---

### 2. What problem does CI/CD solve?
**Answer:**  
- Removes **manual errors** in deployments.  
- Speeds up **release cycles**.  
- Provides **confidence in code quality**.  
- Ensures **consistent environments** across Dev, QA, and Prod.

---

### 3. What’s the difference between Continuous Delivery and Continuous Deployment?
**Answer:**  
- **Continuous Delivery:** Automated deployment ready → but requires manual approval before production.  
- **Continuous Deployment:** No manual intervention → every change passing tests is deployed to production.

---

### 4. Explain the CI/CD pipeline flow.
**Answer:**  
1. **Source Stage:** Developer commits → triggers pipeline.  
2. **Build Stage:** Application compiled, containerized.  
3. **Test Stage:** Unit, integration, and security tests run.  
4. **Deploy Stage:** Code deployed to staging/prod (AWS EC2, ECS, Lambda).  
5. **Monitor Stage:** Metrics/logs observed with Prometheus, Grafana, CloudWatch.

---

### 5. What are popular CI/CD tools?
**Answer:**  
- Jenkins, GitHub Actions, GitLab CI, Bitbucket Pipelines, AWS CodePipeline, Azure DevOps.  
- Choice depends on ecosystem integration (e.g., GitHub Actions for GitHub repos, AWS CodePipeline for AWS workloads).

---

### 6. How do you implement CI/CD in AWS?
**Answer:**  
- **CodeCommit** for source control.  
- **CodeBuild** for builds and tests.  
- **ECR** for Docker images.  
- **CodeDeploy/ECS/Lambda** for deployments.  
- **CodePipeline** as orchestrator.  

---

### 7. What is the role of Docker in CI/CD?
**Answer:**  
- Provides **consistent environments**.  
- Docker images used as build artifacts.  
- Enables **fast rollback** (just redeploy previous image).  
- Works seamlessly with Kubernetes, ECS, and GitHub Actions.

---

### 8. What is the difference between GitHub Actions and Jenkins?
**Answer:**  
- **Jenkins:** Open-source, plugin-rich, customizable, requires infra maintenance.  
- **GitHub Actions:** Cloud-native, YAML workflows, deeply integrated with GitHub repos, faster setup.

---

### 9. What are CI/CD best practices?
**Answer:**  
- Keep builds **fast and reliable**.  
- Automate everything (tests, builds, deployments).  
- Secure secrets using Vault, AWS Secrets Manager, GitHub Secrets.  
- Use **blue-green or canary deployments** for production.  
- Monitor pipelines with dashboards.

---

### 10. What is a build artifact?
**Answer:**  
An output of the build stage (e.g., JAR, WAR, Docker image, Helm chart) that is deployed to staging/production.

---

### 11. What are the common stages in a CI/CD pipeline?
**Answer:**  
- Source → Build → Test → Deploy → Monitor.  

---

### 12. What are the challenges in setting up CI/CD?
**Answer:**  
- Environment differences.  
- Secrets management.  
- Flaky tests.  
- Large monolithic apps.  
- Cloud costs.

---

### 13. How do you integrate testing in CI/CD?
**Answer:**  
- Unit tests (JUnit, PyTest).  
- Integration tests (Postman, Selenium).  
- Security scans (SonarQube, OWASP ZAP).  
- Automated before deployment.

---

### 14. What is Infrastructure as Code (IaC) in CI/CD?
**Answer:**  
IaC automates infra provisioning alongside app deployment. Example: Terraform provisioning EC2 + S3 integrated into pipeline.

---

### 15. How does monitoring fit into CI/CD?
**Answer:**  
Monitoring (CloudWatch, Prometheus, Grafana) ensures deployed apps are healthy. Feedback triggers rollback if issues arise.

---

### 16. What’s the difference between Jenkins and GitHub Actions?
**Answer:**  
- Jenkins: Self-hosted, plugin ecosystem.  
- GitHub Actions: Cloud-managed, YAML config, limited to GitHub repos.

---

### 17. How do you handle secrets in pipelines?
**Answer:**  
- Use AWS Secrets Manager, Vault, or GitHub Secrets.  
- Never hardcode credentials.  
- Encrypt secrets at rest and in transit.

---

### 18. How do you achieve zero downtime deployment?
**Answer:**  
- Blue-Green deployments.  
- Rolling updates with Kubernetes/ECS.  
- Canary deployments.  
- Load balancers shifting traffic gradually.

---

### 19. What’s the difference between CI/CD in monoliths vs microservices?
**Answer:**  
- Monolith: One pipeline for entire app.  
- Microservices: Independent pipelines per service.

---

### 20. How do you measure CI/CD success?
**Answer:**  
- **Deployment Frequency**  
- **Lead Time for Changes**  
- **Mean Time to Recover (MTTR)**  
- **Change Failure Rate**  
These are **DORA metrics** widely used in DevOps/SRE.

---

## 🛠 Practical: Deploy Dockerized App to AWS via GitHub Actions

1. Developer pushes code → triggers GitHub Actions pipeline.  
2. Pipeline builds Docker image → pushes to **AWS ECR**.  
3. ECS service pulls latest image → deploys containers.  
4. **CloudWatch + Prometheus** monitor app health.  
5. Rollback if errors detected.

---

## ✅ Key Takeaways
- Week 2 Revision → Git, CI/CD, Docker, Jenkins, GitHub Actions.  
- 20 Interview Questions → with real-world AWS examples.  
- Practical CI/CD pipeline: GitHub Actions → Docker → AWS ECS.  
- Metrics (DORA) → used in DevOps & SRE interviews.

---
