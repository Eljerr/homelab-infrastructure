# Enterprise-Grade Homelab: Zero-Trust Gateway & Full-Stack Monitoring

## 📌 Executive Summary
This project demonstrates the design and implementation of a scalable, micro-segmented homelab infrastructure. The architecture focuses on high availability, strict security measures, and efficient power consumption by utilizing an Amlogic Single-Board Computer (SBC) as an edge gateway and a Proxmox VE server for application hosting.

## 🏗️ Architecture Topology
The infrastructure is divided into two main physical nodes to ensure security isolation and power efficiency.

1. **Edge Gateway (Amlogic SBC):** Operates 24/7 with a low power footprint. It handles all incoming external traffic via Cloudflare Zero Trust and acts as a reverse proxy using Nginx. 
2. **Compute Node (Proxmox VE):** Hosts isolated Linux Containers (LXC) for specific workloads (Applications, Databases, and Security Operations).

> **Traffic Flow:** `Internet` ➔ `Cloudflare Tunnel` ➔ `STB (Nginx Reverse Proxy)` ➔ `Proxmox LXC (Internal IP)`

## 🛠️ Technology Stack
* **Virtualization & OS:** Proxmox VE, LXC, Ubuntu Server, Debian 11.
* **Networking & Security:** Cloudflare Zero Trust (Tunnels), Nginx, UFW (Uncomplicated Firewall), SSH RSA/Ed25519 Keys.
* **Containerization:** Docker, Docker Compose.
* **Observability:** Prometheus, Grafana, cAdvisor, Node Exporter, Uptime Kuma.

## 🔒 Security Posture & Hardening
Security is implemented at multiple layers, carrying over best practices from bare-metal SBC configurations to virtualized environments:
* **Zero-Trust Network Access:** Port forwarding is strictly disabled on the ISP router. All public access is securely tunneled via Cloudflared.
* **Access Control:** Root login over SSH is disabled across all nodes. Authentication is strictly enforced using Asymmetric SSH Keys.
* **Micro-segmentation:** Workloads are isolated in dedicated LXC instances (`app-server`, `db-server`, `sec-ops`) with internal firewall rules allowing only necessary internal port communication.

## 📊 Full-Stack Observability
A centralized monitoring approach is deployed to track both hardware and containerized environments:
* **Uptime Kuma:** Hosted on the Edge Gateway (SBC) to provide a 24/7 public status page and external HTTP/Ping monitoring.
* **Prometheus & Grafana:** Hosted on the isolated `sec-ops` LXC.
* **Node Exporter:** Gathers physical host metrics (CPU, RAM, Disk I/O).
* **cAdvisor:** Provides real-time resource usage and performance characteristics of running Docker containers.

## 📸 Dashboards & Status
*(Add screenshots of your Grafana Dashboard and Uptime Kuma Public Status Page here)*
* [Screenshot: Grafana Infrastructure Dashboard]
* [Screenshot: Uptime Kuma Public Status]

## 🚀 Future Roadmap
- [ ] Implement CI/CD Pipeline using GitHub Actions and Self-Hosted Runners for automated application deployment.
- [ ] Implement Automated Database Backup to secure cloud storage.