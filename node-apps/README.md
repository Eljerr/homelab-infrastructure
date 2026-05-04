# 🖥️ App Server

## 📌 System Identity
| Key | Value |
| :--- | :--- |
| **Hostname** | app-server-xlc |
| **IP Address** | 192.168.x.x |
| **OS** | Ubuntu Server 22.04 LTS |
| **Main Path** | `/opt/apps/node-apps` |

---

## 🏗️ Monitoring Stack
| Service | Image | Port | Access | Fungsi |
| :--- | :--- | :--- | :--- | :--- |
| **Node Exporter** | `prom/node-exporter` | 9100 | Local | Metrics OS (CPU, RAM, Disk) |
| **cAdvisor** | `gcr.io/cadvisor` | 8080 | Local | Metrics Container Runtime |

---

## 🔒 Security & Hardening
- [ ] **SSH:** Root login disabled & Port hardening.
- [ ] **Auth:** SSH Key-based authentication only.
- [ ] **Firewall:** UFW active 
- [ ] **Access:** User `deploy` (Non-sudoer).
- [ ] **Docker:** User `deploy` masuk ke group `docker` (Rootless execution).

---

