# 🖥️ App Server

## 📌 Server Info
| Key | Value |
|-----|-------|
| **Hostname** | app-server |
| **IP** | 192.168.x.x |
| **OS** | Ubuntu Server xx.xx |
| **Role** | Application Server |
| **Location** | /opt/apps/node-apps |

---

## 🏗️ Stack
| Service | Image | Port | Fungsi |
|---------|-------|------|--------|
| node-exporter | prom/node-exporter | 9100 | Metrics sistem host |
| cadvisor | gcr.io/cadvisor/cadvisor | 8080 | Metrics Docker container |

---

## 🔒 Security
- [ ] Root login SSH disabled
- [ ] SSH Key only
- [ ] UFW aktif
- [ ] User deploy tanpa sudo


