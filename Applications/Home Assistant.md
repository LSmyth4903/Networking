# 🏠 Home Assistant Setup – Homelab

This blog documents my Home Assistant setup in my homelab. I'm using it to monitor server stats and control a few smart lights, while learning about local automation, IoT protocols, and internal networking.

---

## 📘 Glossary

- **HAOS:** Home Assistant Operating System, a minimal OS designed just to run Home Assistant.
- **MQTT:** Lightweight messaging protocol used for communication between devices.
- **Zigbee/Z-Wave:** Wireless communication standards for smart home devices.
- **mDNS:** Multicast DNS, allows devices to find each other on a local network without needing a DNS server.
- **Entity:** A single piece of data or control exposed in Home Assistant (e.g. a light, sensor, or switch).

---

## 📦 Setup Specs

- **Platform:** Proxmox virtual machine  
- **VM Specs:**
  - 2 vCPUs  
  - 2GB RAM  
  - 32GB Disk  
- **OS:** Home Assistant Operating System (HAOS)  
- **Network:** Static IP assigned through pfSense on LAN subnet

---

## ⚙️ Installation Steps

1. Downloaded the [Home Assistant KVM image](https://www.home-assistant.io/installation/alternative#kvm)
2. Converted the image to a Proxmox-compatible format
3. Created a new VM with UEFI BIOS and attached the disk
4. Assigned the VM to `vmbr1` and gave it a static IP in pfSense
5. Booted the VM and accessed Home Assistant via `http://<static-ip>:8123`
6. Completed the onboarding wizard

---

## 🖼️ Current Dashboard

So far, I’ve added:

- Proxmox entities exposed via API (CPU, RAM, disk usage)  
- A handful of smart lights (controlled manually or through the UI)  

These are visible on a basic dashboard to help me monitor the server and test simple automations.

<img width="2874" height="1767" alt="image" src="https://github.com/user-attachments/assets/c59259a5-2d3b-4578-a344-ef2af231fd46" />


---

## 🔍 Features Explored So Far

- Web UI for real-time control and monitoring  
- Local user accounts  
- Static IP setup through pfSense  
- Added Proxmox integration for sensor entities  
- Manually added smart lights via integrations

---

## 🤔 Why I’m Using Home Assistant

- Runs entirely on my own network  
- Gives full control over connected devices  
- Makes it easy to experiment with IoT and automation  
- Gives hands-on experience with protocols like MQTT and mDNS  
- Builds knowledge around internal networking and entity/state management

---

## 🧠 What This Setup Lets Me Do

- Monitor my Proxmox server from a central dashboard  
- Control smart lighting locally without relying on cloud services  
- Learn how entities are added, displayed, and automated  
- Set the foundation for expanding into sensors, automations, and local-only IoT control

---

📌 *This file will grow as I integrate more features and devices.*
