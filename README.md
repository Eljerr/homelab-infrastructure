# 🖥️ App Server

## 📌 Server Info
| Key | Value |
|-----|-------|
| **Hostname** | app-server |
| **IP** | 192.168.18.x |
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

## 📁 Struktur Folder

/opt/apps/node-apps/
├── docker-compose.yml
└── apps/
└── (app nanti di sini)

## 🔒 Security
- [ ] Root login SSH disabled
- [ ] SSH Key only
- [ ] UFW aktif
- [ ] User deploy tanpa sudo

## 🏗️ Stack
=== Service ===
[1] api-test 
[2] node-exporter 
[3] cadvisor 
