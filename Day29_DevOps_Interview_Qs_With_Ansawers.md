# Day 29 – Mock Interview (50 Questions + Detailed Answers)

This document is part of the **30 Days DevOps Interview Preparation Challenge**. Today’s focus is a **mock interview session** with **50 curated questions and answers** for candidates with **1–3 years of experience** in **DevOps, SRE, and Cloud Engineering** roles.

---

## Table of Contents

1. What is DevOps?
2. Difference between Agile and DevOps?
3. What are the key benefits of DevOps?
4. What is CI/CD?
5. Difference between Continuous Delivery and Continuous Deployment?
6. What is Git, and why is it used?
7. Explain branching strategies in Git.
8. What is Git rebase vs merge?
9. How do you resolve a Git conflict?
10. Explain Infrastructure as Code (IaC).
11. What is Terraform, and how does it work?
12. Difference between Terraform and CloudFormation?
13. What are Terraform providers?
14. Explain state file in Terraform.
15. What is Ansible?
16. Difference between Ansible, Puppet, and Chef?
17. What are Ansible Playbooks?
18. Explain Ansible inventory.
19. What is Docker?
20. Difference between a container and a virtual machine?
21. Explain Dockerfile and its usage.
22. What are Docker volumes?
23. What is Docker Compose?
24. How do you troubleshoot a container not starting?
25. What is Kubernetes?
26. Difference between Deployment, ReplicaSet, and StatefulSet?
27. Explain Kubernetes Services (ClusterIP, NodePort, LoadBalancer).
28. What are ConfigMaps and Secrets?
29. How do you scale an application in Kubernetes?
30. Explain Kubernetes namespaces.
31. What is Helm?
32. Explain Helm charts and their purpose.
33. What is a CI/CD pipeline?
34. How do you implement CI/CD using GitHub Actions?
35. What is Jenkins, and why is it popular?
36. Difference between Jenkins Pipeline (Declarative vs Scripted)?
37. What are artifacts in CI/CD?
38. What are common CI/CD pipeline stages?
39. What is Prometheus?
40. How does Prometheus work?
41. What is Grafana, and how does it integrate with Prometheus?
42. Difference between push-based and pull-based monitoring?
43. What are alerts in Prometheus?
44. How do you monitor Docker containers?
45. What is logging in DevOps, and why is it important?
46. Tools for centralized logging?
47. What is Cloud Computing?
48. Difference between IaaS, PaaS, and SaaS?
49. Explain AWS services commonly used in DevOps.
50. What are best practices for DevOps engineers?

---

## Q\&A Section

### 1. What is DevOps?

DevOps is a culture and set of practices that bring together software development (Dev) and IT operations (Ops). The goal is to shorten the software development lifecycle while delivering high-quality software continuously. It emphasizes automation, CI/CD, collaboration, and monitoring.

---

### 2. Difference between Agile and DevOps?

* **Agile**: Focuses on iterative development and customer collaboration.
* **DevOps**: Extends Agile by emphasizing automation, deployment, and operations.

Together, Agile builds software quickly, and DevOps ensures it runs reliably.

---

### 3. What are the key benefits of DevOps?

* Faster delivery of software.
* Improved collaboration between dev & ops teams.
* Continuous testing & monitoring.
* Reduced failure rates and faster recovery.

---

### 4. What is CI/CD?

CI/CD stands for **Continuous Integration** and **Continuous Delivery/Deployment**.

* **CI**: Developers frequently merge code changes into a shared repository.
* **CD**: Automates release of validated code to production or staging.

---

### 5. Difference between Continuous Delivery and Continuous Deployment?

* **Continuous Delivery**: Code is automatically prepared for release but requires manual approval to deploy.
* **Continuous Deployment**: Code automatically moves to production without manual approval.

---

### 6. What is Git, and why is it used?

Git is a **distributed version control system** used for tracking changes in code. It helps teams collaborate, manage code history, and branch effectively.

---

### 7. Explain branching strategies in Git.

* **Git Flow**: Feature, develop, release, and master branches.
* **Feature Branching**: Each feature has its own branch.
* **Trunk-Based**: Developers commit directly to main branch frequently.

---

### 8. What is Git rebase vs merge?

* **Merge**: Combines two branches into one, preserving history.
* **Rebase**: Moves or reapplies commits from one branch onto another, resulting in a cleaner history.

---

### 9. How do you resolve a Git conflict?

* Run `git status` to check conflicts.
* Open conflicting files and resolve manually.
* Stage resolved files using `git add`.
* Commit the changes.

---

### 10. Explain Infrastructure as Code (IaC).

IaC means managing and provisioning infrastructure (servers, networks, databases) through code instead of manual processes. Tools: Terraform, CloudFormation, Ansible.

---

### 11. What is Terraform, and how does it work?

Terraform is an **open-source IaC tool** that lets you define infrastructure in a declarative language (HCL). It interacts with providers (AWS, Azure, GCP) to provision resources.

---

### 12. Difference between Terraform and CloudFormation?

* **Terraform**: Multi-cloud, open-source, HCL.
* **CloudFormation**: AWS-specific, JSON/YAML templates.

---

### 13. What are Terraform providers?

Providers are plugins that allow Terraform to interact with cloud platforms or services (e.g., AWS, Azure, Kubernetes).

---

### 14. Explain state file in Terraform.

The state file (`terraform.tfstate`) tracks the current state of infrastructure, helping Terraform determine what changes need to be applied.

---

### 15. What is Ansible?

Ansible is a configuration management tool that automates software provisioning, configuration, and application deployment. It uses YAML playbooks.

---

### 16. Difference between Ansible, Puppet, and Chef?

* **Ansible**: Agentless, YAML-based.
* **Puppet/Chef**: Require agents and have steeper learning curves.

---

### 17. What are Ansible Playbooks?

Playbooks are YAML files that define a set of tasks to configure systems.

---

### 18. Explain Ansible inventory.

Inventory is a list of hosts or servers managed by Ansible, defined in INI or YAML format.

---

### 19. What is Docker?

Docker is a platform to build, ship, and run applications inside lightweight containers.

---

### 20. Difference between a container and a virtual machine?

* **Container**: Lightweight, shares host OS kernel.
* **VM**: Heavy, runs its own OS.

---

### 21. Explain Dockerfile and its usage.

A Dockerfile is a script containing instructions to build a Docker image.

---

### 22. What are Docker volumes?

Volumes are used to persist data generated by containers.

---

### 23. What is Docker Compose?

Docker Compose is a tool to define and manage multi-container applications using a `docker-compose.yml` file.

---

### 24. How do you troubleshoot a container not starting?

* Check logs using `docker logs`.
* Verify image correctness.
* Inspect container using `docker inspect`.

---

### 25. What is Kubernetes?

Kubernetes (K8s) is a container orchestration platform that automates deployment, scaling, and management of containerized apps.

---

### 26. Difference between Deployment, ReplicaSet, and StatefulSet?

* **Deployment**: Manages stateless applications.
* **ReplicaSet**: Ensures desired number of pod replicas.
* **StatefulSet**: Manages stateful apps with persistent identity.

---

### 27. Explain Kubernetes Services (ClusterIP, NodePort, LoadBalancer).

* **ClusterIP**: Default, accessible only within cluster.
* **NodePort**: Exposes service on each node’s IP at a static port.
* **LoadBalancer**: Exposes service externally using cloud load balancer.

---

### 28. What are ConfigMaps and Secrets?

* **ConfigMap**: Stores non-confidential config data.
* **Secret**: Stores sensitive info (passwords, tokens).

---

### 29. How do you scale an application in Kubernetes?

* Run `kubectl scale deployment <name> --replicas=N`.
* Or use **Horizontal Pod Autoscaler (HPA)**.

---

### 30. Explain Kubernetes namespaces.

Namespaces logically partition cluster resources and provide isolation for teams or applications.

---

### 31. What is Helm?

Helm is a package manager for Kubernetes, simplifying app deployment using charts.

---

### 32. Explain Helm charts and their purpose.

Charts are Helm packages containing templates for Kubernetes manifests.

---

### 33. What is a CI/CD pipeline?

A CI/CD pipeline automates code build, test, and deployment.

---

### 34. How do you implement CI/CD using GitHub Actions?

* Define workflows in `.github/workflows/`.
* Use triggers like `push` or `pull_request`.
* Define jobs for build, test, and deploy.

---

### 35. What is Jenkins, and why is it popular?

Jenkins is an open-source automation server for building, testing, and deploying code. It’s popular due to plugins and flexibility.

---

### 36. Difference between Jenkins Pipeline (Declarative vs Scripted)?

* **Declarative**: Easier, structured syntax.
* **Scripted**: More powerful, Groovy-based.

---

### 37. What are artifacts in CI/CD?

Artifacts are build outputs like `.jar`, `.war`, or Docker images stored for deployment.

---

### 38. What are common CI/CD pipeline stages?

* Source → Build → Test → Deploy → Monitor.

---

### 39. What is Prometheus?

Prometheus is an open-source monitoring and alerting toolkit designed for reliability and scalability.

---

### 40. How does Prometheus work?

Prometheus pulls metrics from targets at intervals, stores them in a time-series database, and allows querying using PromQL.

---

### 41. What is Grafana, and how does it integrate with Prometheus?

Grafana is a visualization tool that integrates with Prometheus to display metrics via dashboards.

---

### 42. Difference between push-based and pull-based monitoring?

* **Push-based**: Clients push metrics to the server.
* **Pull-based**: Server scrapes metrics from clients (Prometheus).

---

### 43. What are alerts in Prometheus?

Alerts are rules defined to notify when metrics cross thresholds, sent via Alertmanager.

---

### 44. How do you monitor Docker containers?

* Use `docker stats` for live metrics.
* Use Prometheus Node Exporter + cAdvisor.

---

### 45. What is logging in DevOps, and why is it important?

Logging captures application and system events, crucial for debugging, auditing, and monitoring.

---

### 46. Tools for centralized logging?

* ELK Stack (Elasticsearch, Logstash, Kibana).
* Splunk.
* Fluentd.

---

### 47. What is Cloud Computing?

Cloud computing provides on-demand delivery of IT resources over the internet with pay-as-you-go pricing.

---

### 48. Difference between IaaS, PaaS, and SaaS?

* **IaaS**: Infrastructure (AWS EC2).
* **PaaS**: Platform (Heroku, AWS Elastic Beanstalk).
* **SaaS**: Software (Gmail, Salesforce).

---

### 49. Explain AWS services commonly used in DevOps.

* **EC2**: Compute.
* **S3**: Storage.
* **EKS**: Kubernetes.
* **CloudWatch**: Monitoring.
* **IAM**: Access management.

---

### 50. What are best practices for DevOps engineers?

* Automate everything.
* Use version control for infra and code.
* Monitor & log all services.
* Security-first approach.
* Collaborate across teams.

---

✅ With these 50 Q\&A, you’ll be well-prepared for DevOps, SRE, and Cloud Engineer interviews with 1–3 years of experience.
