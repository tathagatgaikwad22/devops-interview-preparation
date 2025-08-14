📅 Day 11 – GitHub Actions: Basic Workflow YAML
📖 Theory
What is GitHub Actions?
GitHub Actions is a native CI/CD and automation platform inside GitHub that allows you to:
Automate testing and deployment workflows.
Run jobs on GitHub’s hosted servers or your own self-hosted runners.
Integrate seamlessly with GitHub repositories and events like pushes, pull requests, releases, etc.

Key Concepts:
Workflow → An automated process, defined in .github/workflows/*.yml.
Event → A trigger that starts the workflow (e.g., push, pull_request, schedule, workflow_dispatch).
Job → A set of steps executed in a specific runner environment.
Step → Individual commands or prebuilt reusable actions.
Runner → The machine that executes the job (GitHub-hosted or self-hosted).

🛠 Practical Example 1 – Basic Node.js Workflow
This workflow:
Runs on every push to main.
Checks out the repository.
Installs dependencies.
Runs tests.

yaml
name: Node.js CI

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test

🛠 Practical Example 2 – Deploying to AWS EC2
yaml
name: Deploy to AWS EC2

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
      - name: Deploy to AWS EC2
        env:
          HOST: ${{ secrets.AWS_HOST }}
          USER: ${{ secrets.AWS_USER }}
          KEY: ${{ secrets.AWS_SSH_KEY }}
        run: |
          echo "$KEY" > key.pem
          chmod 400 key.pem
          scp -i key.pem -o StrictHostKeyChecking=no ./build.zip $USER@$HOST:/home/ec2-user/
          ssh -i key.pem -o StrictHostKeyChecking=no $USER@$HOST "unzip -o build.zip && pm2 restart app"

Setting up secrets in GitHub:
Go to Repository → Settings → Secrets and variables → Actions.

Add:
AWS_HOST → EC2 public IP
AWS_USER → ec2-user or ubuntu
AWS_SSH_KEY → Private SSH key for EC2 access.

💡 Why This is Important for DevOps Interviews
GitHub Actions is heavily used in:
Automating builds and deployments.
Integrating with cloud providers (AWS, GCP, Azure).
Running quality checks before merging code.
You’ll often be tested on:
YAML syntax for workflows.
Triggering workflows only on certain events/branches.
Using secrets securely.
Deploying to environments from GitHub Actions.

❓ Common Interview Questions
Q1: How do you trigger a GitHub Action only for the develop branch?
A:

yaml
on:
  push:
    branches:
      - develop
Q2: Where should sensitive credentials be stored?
A: GitHub Secrets under repository settings.

Q3: How do you run jobs in parallel?
A: Define multiple jobs under jobs: without dependencies.

Q4: How do you trigger workflows manually?
A: Use workflow_dispatch.

Q5: What’s the difference between self-hosted and GitHub-hosted runners?
A:
GitHub-hosted: Managed by GitHub, ready-to-use VMs.
Self-hosted: Your own server/VM, more customization.

✅ Key Takeaways
YAML defines the automation steps for GitHub Actions.
Store all sensitive data in Secrets.
Separate jobs into build, test, and deploy stages.
Use events to control when workflows run.
Integrate with cloud platforms for real deployments.

