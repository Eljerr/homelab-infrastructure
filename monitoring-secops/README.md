# Monitoring & SecOps Server (`sec-ops`)

## 📌 Overview
This directory contains the observability stack configurations, including Prometheus, Grafana, and related exporters to monitor the health and performance of the entire homelab infrastructure.

## 🖥️ Environment Details
- **Hostname:** `sec-ops`
- **Environment:** Proxmox LXC (Linux Container)
- **Deployment Path:** `/opt/apps/monitoring-secops`
- **Role:** Infrastructure Monitoring, Metrics Collection, and Security Operations

## ⚙️ Features & Architecture
- **Prometheus:** Acts as the central time-series database, scraping metrics from `node-exporter` (hardware/OS metrics) and `cadvisor` (container metrics) across all physical and virtual nodes.
- **Grafana:** Visualizes the metrics scraped by Prometheus via rich, customizable dashboards.
- **Centralized Alerting:** Configurable to send notifications to administrators in the event of downtime, resource exhaustion, or unusual network activity.

## 🚀 How to Run/Deploy
Since the repository is managed using sparse-checkout, this node only pulls this specific directory.

```bash
# 1. Navigate to the deployment path
cd /opt/apps/monitoring-secops

# 2. Pull the latest repository changes
git pull origin main

# 3. Start or update the monitoring stack
docker-compose up -d
```
