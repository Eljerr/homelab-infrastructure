# Edge Gateway (`stb`)

## 📌 Overview
This directory holds the setup and configuration for the Edge Gateway, which acts as the main entry point and reverse proxy for all external traffic entering the homelab network.

## 🖥️ Environment Details
- **Hostname:** `stb`
- **Hardware:** AKARI AX810 (Amlogic S905X4 Single-Board Computer)
- **Deployment Path:** `/home/<user>/gateway-stb`
- **Role:** Reverse Proxy, Zero-Trust Tunnel Gateway, & Uptime Monitoring

## ⚙️ Features & Architecture
- **Cloudflare Zero Trust:** Runs the `cloudflared` daemon to securely expose internal services to the internet without opening any incoming ports on the ISP router.
- **Nginx Reverse Proxy:** Routes incoming, authenticated traffic to the appropriate internal LXC nodes (`app-server`, `db-server`, etc.).
- **High Availability & Efficiency:** Deployed on an ARM-based SBC with extremely low power consumption, allowing the gateway to run 24/7 independently of the main Proxmox compute node.

## 🚀 How to Run/Deploy
Since the repository is managed using sparse-checkout, this node only pulls this specific directory.

```bash
# 1. Navigate to the deployment path
cd ~/gateway-stb

# 2. Pull the latest repository changes
git pull origin main

# 3. Start or update the gateway services
docker-compose up -d
```
