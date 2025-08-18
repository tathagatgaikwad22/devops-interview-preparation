Day 16 – DevOps Interview Preparation Challenge
Topic: Dockerfile + Compose (Multi-Container App)
📌 Introduction

Docker has revolutionized how applications are built, shipped, and run. Today, we focus on:

Writing a Dockerfile to containerize applications.

Using Docker Compose to orchestrate multi-container applications.

Learning the interview questions and practical examples around Docker.

This topic is extremely important for DevOps, Cloud, and SRE interviews since containerization and orchestration are core concepts.

🛠 What is a Dockerfile?

A Dockerfile is a script that contains instructions to build a Docker image. It defines:

The base image.

Dependencies required by the application.

Commands to run during image build.

The startup process (ENTRYPOINT or CMD).

Example: Simple Python App Dockerfile

# Base Image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements and install
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Expose port
EXPOSE 5000

# Run app
CMD ["python", "app.py"]

🛠 What is Docker Compose?

Docker Compose is a tool for defining and running multi-container applications using a YAML file (docker-compose.yml).
It allows you to:

Run multiple containers together (e.g., app + database).

Define environment variables, volumes, networks.

Simplify development and testing.

Example: Multi-Container App (Flask + MySQL)

version: '3.9'

services:
  web:
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - db
    environment:
      - DB_HOST=db
      - DB_USER=root
      - DB_PASS=password

  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: flaskdb
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:

🚀 Practical on AWS
Step 1: Install Docker & Docker Compose on EC2
sudo apt update
sudo apt install -y docker.io docker-compose
sudo systemctl enable docker
sudo usermod -aG docker ubuntu

Step 2: Clone Your App Repo
git clone https://github.com/your-username/flask-docker-app.git
cd flask-docker-app

Step 3: Build and Run with Compose
docker-compose up --build -d

Step 4: Verify

Flask app → http://<EC2-Public-IP>:5000

MySQL DB is running in the background.

📖 Theory Recap

Dockerfile → Defines how an image is built.

Docker Image → Immutable template created from a Dockerfile.

Docker Container → Running instance of a Docker image.

Docker Compose → Orchestrates multi-container applications with a simple YAML.

❓ Interview Questions & Answers
Q1. What is the difference between Dockerfile and Docker Compose?

Answer:

Dockerfile → Defines how to build a single image.

Docker Compose → Defines and runs multiple containers together using those images.

Q2. How do you persist data in Docker containers?

Answer:
By using volumes in Docker Compose or -v in Docker run.
Example:

volumes:
  - db_data:/var/lib/mysql


This ensures data is not lost when the container restarts.

Q3. How does depends_on work in Docker Compose?

Answer:
depends_on ensures one service starts before another, but it doesn’t guarantee readiness. For DB readiness, you need health checks or wait-for-scripts.

Q4. How do you reduce image size in Dockerfile?

Answer:

Use slim base images (e.g., python:3.9-slim).

Use .dockerignore to exclude unnecessary files.

Use multi-stage builds.

Clean cache after installs (apt-get clean && rm -rf /var/lib/apt/lists/*).

Q5. How would you secure secrets in Docker Compose?

Answer:

Do not hardcode secrets in docker-compose.yml.

Use environment files (.env).

Use AWS Secrets Manager, Vault, or Docker secrets for production.

Q6. What are some real-world use cases of Docker Compose?

Answer:

Running local development environments (app + DB + cache).

Setting up CI/CD test environments.

Quickly spinning up multi-service microservices apps.

Q7. Can Docker Compose be used in production?

Answer:
Yes, but limited. It’s mostly for dev/test. In production, we use Kubernetes, ECS, or Swarm for large-scale orchestration.

✅ Key Takeaways

Dockerfile = Blueprint for building images.

Docker Compose = Orchestrates multiple containers.

Essential for interviews as it tests both hands-on and conceptual skills.

Practice deploying on AWS EC2 for real-world confidence.
