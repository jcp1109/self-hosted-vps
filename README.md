# 🚀 Self-Hosted RustDesk & Pi-hole on a Free VPS with Docker  

## Overview  

This project sets up **RustDesk Server** (self-hosted remote desktop) and **Pi-hole** (network-wide ad blocker) on a **free-tier VPS** using **Docker**.  

🔹 **Why?**  
- Secure remote access **without third-party reliance**  
- Ad-blocking at the **network level** for better privacy  
- Cost-effective, leveraging **cloud free tiers**  

🔹 **How?**  
- **Docker & Docker Compose** for easy deployment  
- **Cloud networking & firewall configurations**  
- **Always-Free VPS (Oracle Cloud)** but works with any provider  

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
