# 🛡️ SecOps Monitoring Server

## 📌 System Identity
| Key | Value |
| :--- | :--- |
| **Hostname** | secops-xlc |
| **IP Address** | 192.168.x.x |
| **OS** | Ubuntu Server 22.04 LTS |
| **Environment** | Production / Monitoring |
| **Main Path** | `/opt/apps/monitoring-secops` |

---

## 🏗️ Monitoring Stack
| Service | Image | Port | Access | Fungsi |
| :--- | :--- | :--- | :--- | :--- |
| **Prometheus** | `prom/prometheus` | 9090 | Internal | Data Aggregator & TSDB |
| **Grafana** | `grafana/grafana` | 3000 | Public/Local | Visualisasi & Dashboard |
| **Node Exporter** | `prom/node-exporter` | 9100 | Local | Metrics OS (CPU, RAM, Disk) |
| **cAdvisor** | `gcr.io/cadvisor` | 8080 | Local | Metrics Container Runtime |

---

## 🔒 Security & Hardening
- [ ] **SSH:** Root login disabled & Port hardening.
- [ ] **Auth:** SSH Key-based authentication only.
- [ ] **Firewall:** UFW active (Hanya buka port 3000, 9090, 22).
- [ ] **Access:** User `deploy` (Non-sudoer).
- [ ] **Docker:** User `deploy` masuk ke group `docker` (Rootless execution).

---

