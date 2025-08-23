# Day 22: Terraform Basics – Provider, Init, Plan

Welcome to **Day 22** of the *30 Days DevOps Interview Preparation Challenge*!  
Today's topic focuses on the Terraform basics: **Providers, terraform init, and terraform plan**.

---

## 🌍 What is Terraform?
Terraform is an open-source Infrastructure as Code (IaC) tool developed by HashiCorp.  
It allows you to define cloud and on-prem infrastructure using a declarative configuration language (HCL).  

Key benefits:  
- Automates infrastructure provisioning  
- Consistent deployments across environments  
- Supports multiple providers (AWS, Azure, GCP, Kubernetes, etc.)  
- Enables version control of infrastructure

---

## 🔑 Core Concepts of Day 22

### 1. Provider
- A **provider** is a plugin that allows Terraform to interact with APIs of cloud platforms or services.  
- Examples: AWS, Azure, GCP, Kubernetes, Docker.  
- Providers must be defined in the `.tf` configuration file.

**Example:**  
```hcl
provider "aws" {
  region = "us-east-1"
}
```

👉 Terraform downloads providers during initialization.

---

### 2. `terraform init`
- The first command you run in a new Terraform project.  
- Initializes the working directory with all necessary dependencies.  
- Downloads provider plugins.  
- Configures the backend for storing state (if defined).  

**Command:**  
```bash
terraform init
```

**Output (sample):**  
```
Initializing the backend...
Initializing provider plugins...
Terraform has been successfully initialized!
```

---

### 3. `terraform plan`
- Creates an **execution plan**.  
- Shows what Terraform intends to do before applying changes.  
- Lists resources to be created, updated, or destroyed.  

**Command:**  
```bash
terraform plan
```

**Sample output:**  
```
+ aws_instance.my_ec2
    ami: "ami-0c55b159cbfafe1f0"
    instance_type: "t2.micro"
```

This tells you that a new EC2 instance will be created.

---

## 📝 Interview Preparation – Sample Questions & Answers

**Q1. What is a provider in Terraform?**  
👉 A provider is a plugin used by Terraform to interact with APIs of supported services (AWS, Azure, GCP, etc.). It defines which infrastructure platform Terraform will manage.

**Q2. What happens when you run `terraform init`?**  
👉 It initializes the project, downloads the necessary provider plugins, and configures the backend. Without `init`, Terraform commands like `plan` or `apply` won’t work.

**Q3. What is the difference between `terraform plan` and `terraform apply`?**  
👉 `plan` shows the execution plan without making changes. `apply` actually makes changes to the infrastructure.

**Q4. Why is running `terraform plan` important?**  
👉 It helps you preview changes and avoid unintentional infrastructure modifications.

**Q5. How does Terraform know which provider plugins to install?**  
👉 From the `provider` block defined in the `.tf` file and from the Terraform Registry.

---

## ✅ Pro Tips
- Always run `terraform plan` before `terraform apply`.  
- Store Terraform state files securely (use remote backends like S3 + DynamoDB).  
- Use versioned providers for consistency across environments.

---

## 🚀 Conclusion
Understanding the basics of **Providers, Init, and Plan** forms the foundation of Terraform.  
These commands are among the most common areas of questioning in DevOps interviews.

Stay tuned for Day 23! 💡

---

🔗 Follow the full 30 Days DevOps Interview Preparation Challenge for more.  
