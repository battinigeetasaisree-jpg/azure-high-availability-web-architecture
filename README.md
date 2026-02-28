C# Azure High Availability Web Architecture

## 📌 Project Overview
This project demonstrates a High Availability (HA) web architecture deployed on Microsoft Azure using:

- 2 Ubuntu Virtual Machines
- NGINX Web Server
- Azure Standard Public Load Balancer
- HTTP Health Probe
- Backend Pool with multiple VMs

The Load Balancer distributes incoming traffic across two web servers to ensure availability and reliability.

---

## 🏗 Architecture Components

- Resource Group
- Virtual Network + Subnet
- VM-Web-01 (Ubuntu + NGINX)
- VM-Web-02 (Ubuntu + NGINX)
- Public IP (Frontend)
- Backend Pool (Both VMs attached)
- HTTP Health Probe (Port 80)
- Load Balancing Rule

---

## ⚙️ Load Balancing Validation

Traffic was tested using:

```bash
for i in {1..10}; do curl http://<Public-IP>; echo; done

Output showed alternating responses:

Web Server 1
Web Server 2
Web Server 1
Web Server 2
