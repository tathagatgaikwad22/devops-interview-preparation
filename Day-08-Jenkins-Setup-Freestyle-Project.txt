🚀 Day 8 – Jenkins Setup & Freestyle Project
30 Days DevOps Interview Preparation Challenge

📌 Introduction
Jenkins is one of the most widely used open-source automation servers for building, testing, and deploying applications. As a DevOps Engineer, understanding Jenkins setup and its project configurations is essential for CI/CD implementation.

1️⃣ What is Jenkins?
Type: Open-source automation server.

Purpose: Automates build, test, and deployment processes.

Key Features:

Web-based interface

Supports hundreds of plugins

Distributed builds

Supports multiple build tools (Maven, Gradle, etc.)

2️⃣ Why Jenkins is Important in DevOps
Enables Continuous Integration: Frequent code commits are automatically built and tested.

Supports Continuous Delivery/Deployment: Automates pushing code to production.

Improves developer productivity and reduces human error.

Integrates with Git, Docker, Kubernetes, AWS, GCP, Azure.

3️⃣ Jenkins Setup on AWS EC2 (Ubuntu)
Step 1 – Launch EC2 Instance

# Launch Ubuntu 22.04 LTS (t2.micro)
# Open ports: 22 (SSH), 8080 (Jenkins), 80 (optional), 443 (optional)
Step 2 – Install Java (Required for Jenkins)

sudo apt update
sudo apt install fontconfig openjdk-17-jre -y
java -version
Step 3 – Add Jenkins Repository & Install

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y

Step 4 – Start Jenkins Service
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
Step 5 – Access Jenkins
Open browser: http://<EC2-Public-IP>:8080

Retrieve admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Install suggested plugins.

Create admin user.

4️⃣ Creating a Freestyle Project in Jenkins
Steps:

Go to Jenkins Dashboard → New Item.

Enter project name → select Freestyle project → OK.

Configure SCM:

Select Git → enter repository URL.

Add credentials if private.

Build Triggers:

Select Poll SCM or Build periodically or Build when changes are pushed to GitHub.

Build Steps:

Add Execute Shell → write build commands (e.g., mvn clean install or docker build).

Post-build Actions:

Send email, deploy to server, etc.

Save → Click Build Now.

5️⃣ Common Jenkins Interview Questions (with Answers)
Q1: What is a Jenkins Freestyle project?
A Jenkins job type that allows you to configure and execute a sequence of build steps with minimal setup.

Q2: How does Jenkins integrate with GitHub?
By configuring Git plugin and adding webhook from GitHub to Jenkins URL /github-webhook/.

Q3: How do you trigger a Jenkins job automatically?
Webhook triggers from SCM.

Poll SCM schedule.

API triggers via scripts.

Q4: How do you secure Jenkins?
Enable security → Use Role-based access control.

Use credentials plugin for secret management.

Restrict public network access.

Q5: How to store credentials in Jenkins?
Manage Jenkins → Manage Credentials → Add credentials.

Reference them in jobs using the credentials binding plugin.

6️⃣ Best Practices for Jenkins
Use pipelines instead of freestyle for complex CI/CD.

Keep Jenkins updated to avoid security issues.

Use separate build agents for scalability.

Backup Jenkins home directory regularly.


✅ Task for Today:

Install Jenkins on AWS EC2.

Create a Freestyle project pulling code from GitHub and running a simple build.

Document your steps.
