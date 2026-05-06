# Application Server (`app-server`)

## 📌 Overview
This directory contains the application-level workloads. All primary user-facing applications, APIs, and services are hosted within this specific environment.

## 🖥️ Environment Details
- **Hostname:** `app-server`
- **Environment:** Proxmox LXC (Linux Container)
- **Deployment Path:** `/opt/apps/node-apps`
- **Role:** Application Hosting and Execution

## ⚙️ Features & Architecture
- **Containerized Workloads:** All applications are managed via Docker and Docker Compose for easy deployment, versioning, and rollback.
- **Stateless Design:** Services are designed to be stateless where possible, relying entirely on the isolated `db-server` for data persistence.
- **Internal Routing & Security:** Services hosted here do not have public IP addresses or direct internet access. They are strictly routed and accessed through the `gateway-stb` reverse proxy.

## 🚀 How to Run/Deploy
Since the repository is managed using sparse-checkout, this node only pulls this specific directory.

```bash
# 1. Navigate to the deployment path
cd /opt/apps/node-apps

# 2. Pull the latest repository changes
git pull origin main

# 3. Start or update the application workloads
docker-compose up -d
```
