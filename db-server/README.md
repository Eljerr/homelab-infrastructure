# Database Server (`db-server`)

## 📌 Overview
This directory contains the configurations and deployment scripts for the Database Server. This server is designed to handle all persistent data and database workloads for the homelab infrastructure.

## 🖥️ Environment Details
- **Hostname:** `db-server`
- **Environment:** Proxmox LXC (Linux Container)
- **Deployment Path:** `/opt/apps/db-server`
- **Role:** Centralized Database Management

## ⚙️ Features & Architecture
- **Isolation:** Hosted in a dedicated LXC to ensure that database workloads are not affected by application CPU spikes or monitoring overhead.
- **Security:** Internal UFW rules are configured to only accept incoming connections from the `app-server`. Public internet access is completely blocked.
- **Data Persistence:** Container volumes are mapped securely to the Proxmox host disk to ensure data integrity and facilitate easier backups.

## 🚀 How to Run/Deploy
Since the repository is managed using sparse-checkout, this node only pulls this specific directory.

```bash
# 1. Navigate to the deployment path
cd /opt/apps/db-server

# 2. Pull the latest repository changes
git pull origin main

# 3. Start or update the database services
docker-compose up -d
```
