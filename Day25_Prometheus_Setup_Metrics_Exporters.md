# 🚀 Day 25 - DevOps Interview Preparation Challenge

## Topic: Prometheus - Setup, Metrics, Exporters

Welcome to **Day 25 of the 30 Days DevOps Interview Preparation Challenge**. Today, we explore **Prometheus**, one of the most widely used open-source monitoring and alerting tools in DevOps.

---

## 📖 What is Prometheus?

Prometheus is an **open-source monitoring and alerting toolkit**, originally built by SoundCloud. It is now part of the **Cloud Native Computing Foundation (CNCF)**, alongside Kubernetes.

* **Pull-based model** – Prometheus scrapes metrics from targets.
* **Time-series database (TSDB)** – Stores data in time-series format with labels.
* **Powerful query language (PromQL)** – For analyzing metrics.
* **Built-in alert manager** – For alerting and integrations with tools like Slack, PagerDuty, etc.

---

## ⚙️ Prometheus Architecture

* **Prometheus Server**: Scrapes and stores metrics.
* **Exporters**: Collect metrics from applications, nodes, or services.
* **Alertmanager**: Handles alerts.
* **Visualization**: Usually via Grafana.

---

## 🔧 Setting up Prometheus (Locally)

### 1. Download Prometheus

```bash
wget https://github.com/prometheus/prometheus/releases/download/v2.52.0/prometheus-2.52.0.linux-amd64.tar.gz
```

### 2. Extract & Run

```bash
tar xvf prometheus-2.52.0.linux-amd64.tar.gz
cd prometheus-2.52.0.linux-amd64
./prometheus --config.file=prometheus.yml
```

### 3. Access UI

* Open: `http://localhost:9090`

---

## 📊 Metrics in Prometheus

Prometheus collects metrics in **4 main types**:

1. **Counter** → Always increasing (e.g., HTTP requests).
2. **Gauge** → Values that go up/down (e.g., CPU usage).
3. **Histogram** → Measures data distribution (e.g., request durations).
4. **Summary** → Similar to histogram but provides quantiles.

---

## 🔌 Exporters in Prometheus

Exporters are services that **expose metrics in Prometheus format**.

* **Node Exporter** → System metrics (CPU, Memory, Disk).
* **cAdvisor** → Container metrics.
* **Blackbox Exporter** → Endpoint probing.
* **Custom Exporters** → For custom apps.

Example (installing Node Exporter on Linux):

```bash
wget https://github.com/prometheus/node_exporter/releases/download/v1.8.0/node_exporter-1.8.0.linux-amd64.tar.gz
tar xvf node_exporter-1.8.0.linux-amd64.tar.gz
cd node_exporter-1.8.0.linux-amd64
./node_exporter &
```

Access: `http://localhost:9100/metrics`

---

## ❓ Common Prometheus Interview Questions & Answers

### Q1. What makes Prometheus different from other monitoring tools?

**Answer:** Unlike push-based tools, Prometheus uses a **pull model**. It scrapes metrics via HTTP endpoints, stores them in a **time-series database**, and uses PromQL for querying.

---

### Q2. Explain the different metric types in Prometheus.

**Answer:**

* **Counter**: Cumulative metric, only increases.
* **Gauge**: Metric that can increase or decrease.
* **Histogram**: Buckets data into ranges.
* **Summary**: Provides quantiles (percentiles).

---

### Q3. What is an Exporter in Prometheus?

**Answer:** Exporters are agents that expose metrics in a Prometheus-compatible format. For example, Node Exporter exposes system-level metrics.

---

### Q4. How does Prometheus integrate with Grafana?

**Answer:** Grafana uses Prometheus as a **data source** and provides dashboards for visualization of metrics.

---

### Q5. What is PromQL?

**Answer:** PromQL (Prometheus Query Language) is used to query time-series data in Prometheus. Example:

```promql
rate(http_requests_total[5m])
```

This shows the per-second rate of HTTP requests in the last 5 minutes.

---

## 🔐 Best Practices in Prometheus

* Keep scrape intervals reasonable (e.g., 15s for system metrics).
* Use **labels** effectively for filtering.
* Secure endpoints using authentication.
* Use **remote storage integrations** (Thanos, Cortex) for long-term retention.

---

## ✅ Summary

* Prometheus is a **pull-based monitoring system**.
* Metrics are exposed via **exporters**.
* **PromQL** is used for querying.
* Integrated with **Grafana** for visualization.
* Crucial for **DevOps, Kubernetes, and cloud-native monitoring**.

---

📌 This concludes **Day 25 of the 30 Days DevOps Challenge**.
Next up: **Day 26 → Grafana: Dashboards & Visualization** 🎨
