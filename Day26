# 🚀 Day 26 – Prometheus Installation & Setup on AWS EC2 (Ubuntu)

## 📌 Introduction

Prometheus is an **open-source monitoring and alerting system** widely used in DevOps and cloud-native environments.  
It is designed to **collect, store, and query metrics** from applications, servers, containers, and infrastructure.

Today we will learn:

- Why Prometheus is important in cloud monitoring  
- Pre-requisites for AWS EC2 installation  
- Step-by-step installation on Ubuntu (AWS EC2)  
- Adding Node Exporter for system metrics  
- Verification & troubleshooting  

---

## 🔹 Why Prometheus?

- **Time-series database** → Stores data with timestamps.  
- **PromQL (Prometheus Query Language)** → Query and analyze metrics.  
- **Pull model** → Prometheus scrapes metrics from targets instead of pushing.  
- **Lightweight & reliable** → Single binary deployment.  
- **Cloud-native** → Kubernetes, Docker, AWS, and many integrations.  
- **Ecosystem** → Works with Grafana (dashboards) and Alertmanager (alerts).  

---

## 🔹 Pre-requisites on AWS
Before installing Prometheus on AWS, ensure the following:

1. **AWS EC2 Instance**  
   - Ubuntu 20.04 or 22.04 LTS  
   - Instance type: `t2.micro` (for testing) / `t2.medium` (for production)  

2. **Security Group Configuration**  
   - Allow **port 22 (SSH)** from your IP  
   - Allow **port 9090 (Prometheus Web UI)**  
   - Allow **port 9100 (Node Exporter metrics)**  

3. **System Packages Installed**  
   ```bash
   sudo apt update && sudo apt upgrade -y
   sudo apt install wget curl tar -y
🔹 Step-by-Step Installation

1️⃣ Connect to EC2 via SSH
ssh -i your-key.pem ubuntu@<EC2-Public-IP>

2️⃣ Create Prometheus User & Directories
sudo useradd --no-create-home --shell /usr/sbin/nologin prometheus
sudo mkdir /etc/prometheus /var/lib/prometheus
sudo chown prometheus:prometheus /etc/prometheus /var/lib/prometheus

3️⃣ Download & Install Prometheus
VER=2.52.0
cd /tmp
wget https://github.com/prometheus/prometheus/releases/download/v$VER/prometheus-$VER.linux-amd64.tar.gz
tar xvf prometheus-$VER.linux-amd64.tar.gz
cd prometheus-$VER.linux-amd64

sudo cp prometheus /usr/local/bin/
sudo cp promtool /usr/local/bin/
sudo cp -r consoles /etc/prometheus
sudo cp -r console_libraries /etc/prometheus

4️⃣ Create Prometheus Config File
sudo nano /etc/prometheus/prometheus.yml
Paste:
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']

5️⃣ Setup Prometheus Systemd Service
sudo tee /etc/systemd/system/prometheus.service > /dev/null <<'EOF'
[Unit]
Description=Prometheus Monitoring
Wants=network-online.target
After=network-online.target

[Service]
User=prometheus
ExecStart=/usr/local/bin/prometheus \
  --config.file=/etc/prometheus/prometheus.yml \
  --storage.tsdb.path=/var/lib/prometheus \
  --web.listen-address=0.0.0.0:9090

Restart=on-failure

[Install]
WantedBy=multi-user.target
EOF

6️⃣ Start & Enable Prometheus
sudo systemctl daemon-reload
sudo systemctl enable prometheus
sudo systemctl start prometheus
Check status:
systemctl status prometheus

7️⃣ Verify Prometheus
Open your browser:
👉 http://<EC2-Public-IP>:9090
Go to Status → Targets
Run query:
up

🔹 Installing Node Exporter (System Metrics)
1️⃣ Download & Install
VER=1.8.1
cd /tmp
wget https://github.com/prometheus/node_exporter/releases/download/v$VER/node_exporter-$VER.linux-amd64.tar.gz
tar xvf node_exporter-$VER.linux-amd64.tar.gz
sudo cp node_exporter-$VER.linux-amd64/node_exporter /usr/local/bin/

2️⃣ Create Systemd Service
sudo tee /etc/systemd/system/node_exporter.service > /dev/null <<'EOF'
[Unit]
Description=Node Exporter
After=network.target

[Service]
ExecStart=/usr/local/bin/node_exporter
Restart=on-failure

[Install]
WantedBy=multi-user.target
EOF

Start service:
sudo systemctl daemon-reload
sudo systemctl enable node_exporter
sudo systemctl start node_exporter

3️⃣ Update Prometheus Config
sudo nano /etc/prometheus/prometheus.yml
Add:

yaml
Copy code
  - job_name: 'node_exporter'
    static_configs:
      - targets: ['localhost:9100']

Restart Prometheus:
sudo systemctl restart prometheus

🔹 Troubleshooting
Prometheus not starting?
journalctl -u prometheus -f
promtool check config /etc/prometheus/prometheus.yml
Ports blocked?

Check with:

ss -tulpen | grep 9090
Fix in AWS Security Group.

Node Exporter not found?
Check → http://<EC2-Public-IP>:9100/metrics

📌 Summary
✅ In Day 26, we learned:

Why Prometheus is important in cloud monitoring

Pre-requisites for AWS EC2 installation

Installed Prometheus on Ubuntu (EC2)

Configured it as a systemd service

Installed Node Exporter for system metrics

Verified setup via Prometheus Web UI

