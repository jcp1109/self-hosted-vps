Here’s a README.md file for your GitHub repository:

⸻



# 🚀 Self-Hosted Remote Access & DNS Filtering on a Free VPS  

## Overview  

This project sets up **RustDesk Server** (self-hosted remote desktop) and **Pi-hole** (network-wide ad blocker) on a **free-tier VPS** using **Docker**.  

✅ **Cloud-based**: Deployed on an **"Always-Free" Oracle Cloud VPS** (but works on any free-tier VPS).  
✅ **Containerized**: Managed with **Docker & Docker Compose** for easy deployment.  
✅ **Secure & Private**: Eliminates reliance on third-party remote access and DNS filtering services.  

## 🏗 Architecture  

- **VPS**: Free-tier **Oracle Cloud Ubuntu 22.04** instance (1 vCPU, 1GB RAM).  
- **RustDesk Server**: **HBBS** & **HBBR** (RustDesk's relay & broker) for remote desktop access.  
- **Pi-hole**: Ad-blocking DNS resolver with customizable filtering.  
- **Networking**: Open firewall for RustDesk ports `21115-21119` & secure DNS resolution via Pi-hole.  

## 📦 Installation  

### 1️⃣ Provision a Free VPS  
Get a **free-tier VPS** from **Oracle Cloud** (recommended) or another cloud provider. Use **Ubuntu 22.04** for compatibility.  

### 2️⃣ Install Docker & Docker Compose  
```bash
sudo apt update && sudo apt install -y docker.io docker-compose
sudo systemctl enable --now docker

3️⃣ Clone & Deploy

git clone https://github.com/yourusername/self-hosted-vps.git
cd self-hosted-vps
docker-compose up -d

4️⃣ Configure Services
	•	RustDesk: Point your clients to your VPS IP.
	•	Pi-hole: Set as your device’s DNS resolver.

🔧 Configuration

Modify docker-compose.yml to adjust settings:

services:
  rustdesk:
    image: rustdesk/rustdesk-server
    ports:
      - "21115-21119:21115-21119"
    restart: always

  pihole:
    image: pihole/pihole
    environment:
      - DNS1=1.1.1.1
      - DNS2=8.8.8.8
    ports:
      - "53:53/tcp"
      - "53:53/udp"
      - "80:80/tcp"
    restart: always

🔥 Key Features

✔ Self-hosted RustDesk: Secure remote access without third-party reliance.
✔ Network-wide ad blocking: Pi-hole removes ads & trackers across all devices.
✔ Lightweight VPS deployment: Runs efficiently on a free-tier cloud instance.
✔ Dockerized: Simplifies deployment & scaling.

🌟 Future Enhancements
	•	Automate with Terraform & Ansible
	•	Integrate Cloudflare tunnels for better security
	•	Add monitoring & logging with Prometheus & Grafana

🤝 Contribute

Pull requests & suggestions are welcome! Fork this repo, make improvements, and submit a PR.

📌 GitHub Repo: https://github.com/yourusername/self-hosted-vps

⸻

🛠 Built with Docker, Cloud Networking, & Self-Hosting Principles

---

This README effectively highlights **cloud, networking, Docker, and self-hosting** skills, making it relevant for **SRE and DevOps roles**. Let me know if you want any modifications!