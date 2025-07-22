# 🧠 Week 1: Building My First Homelab - Networking & Self-Hosting Foundations

This week marked the beginning of my journey into networking and self-hosting. I’m a final-year Computer Science student, and while I’ve covered a lot of theory at university, I wanted to get more hands-on. I took an old Dell OptiPlex, installed Proxmox on it, and started building out my lab from scratch. These are personal notes I’m keeping as I go - not polished tutorials - just documenting what I did, what worked, what didn’t, and what I learned.

---

## 🧾 Glossary (Important Concepts I Learned This Week)
- **pfSense** - An open-source firewall and router operating system. It controls the flow of data between your home network and the internet, filtering traffic to keep things secure.
- **Firewall** - A security system that monitors and controls incoming and outgoing network traffic based on predetermined rules.
- **WAN/LAN** - WAN (Wide Area Network) refers to your external network connection like the internet; LAN (Local Area Network) is your internal network where your devices connect.
- **Static IP** - A fixed IP address manually assigned to a device, so it doesn’t change over time.
- **SSH (Secure Shell)** - A protocol that lets you securely connect and control a remote computer’s command line.
- **Nmap** - A network scanning tool that discovers devices on a network and what services they offer.
- **Subnet** - A segment of a network, defined by an IP address range, which helps organize and secure networks.
- **UFW (Uncomplicated Firewall)** - A simple tool for managing firewall rules on Linux systems.
- **Home Assistant** - A platform for managing smart devices locally, giving more privacy and control compared to cloud-based systems.
- **IoT (Internet of Things)** - Physical devices like smart bulbs, plugs, and sensors connected to your network.

---

## ✅ Goals for the Week
- Start building a personal homelab to learn practical networking and self-hosting
- Get comfortable using networking tools and Linux environments
- Experiment and troubleshoot to deepen understanding
- Document everything clearly for future reference

---

## 🔐 Set Up pfSense Firewall
**What it is:** pfSense is an open-source firewall and router OS. It acts as a gatekeeper between your home network and the internet, filtering traffic, managing IP addresses, and helping segment your network.

**How it works:** pfSense inspects data packets entering and leaving your network and applies rules to allow or block traffic, helping protect your devices from unwanted access.

**What I did:**
- Downloaded the pfSense ISO and installed it as a VM on Proxmox
- Assigned network interfaces for WAN (internet side) and LAN (local network side)
- Ran the initial setup wizard to configure interfaces and enable DHCP for assigning IP addresses on the LAN
- Accessed the pfSense web dashboard to tweak firewall settings and set up a strong password

**What this allowed me to do:**  
Control how devices in my network connect to each other and to the internet, and get hands-on experience with firewall and routing basics.

---

## 🖥️ Installed Ubuntu Server + SSH
**What it is:** Ubuntu Server is a Linux operating system without a graphical interface, designed for running applications and services on servers.

**How it works:** It provides a lightweight environment that you manage via command line, ideal for running background services and learning Linux server management.

**What I did:**
- Created a VM in Proxmox and installed Ubuntu Server using the ISO
- Installed and configured OpenSSH to enable secure remote terminal access
- Retrieved the server’s IP address from pfSense DHCP leases
- Connected to the server using SSH from another machine
- Created a regular user account and set up UFW firewall rules for basic protection

**What this allowed me to do:**  
Practice remotely managing servers, a key skill in both networking and cybersecurity, and become comfortable with Linux command line basics.

---

## 🔎 Used Nmap to Explore My Network
**What it is:** Nmap is a powerful command-line tool used to discover devices and services on a network by sending packets and analyzing responses.

**How it works:** Nmap scans IP ranges to identify active devices, open ports, and services, giving you a map of what’s on your network and potential vulnerabilities.

**What I did:**
- Ran a ping scan (`nmap -sn 192.168.1.0/24`) to find live devices on my subnet
- Scanned specific IP addresses (`nmap -sV 192.168.1.X`) to detect open ports and software versions
- Learned how different devices reveal themselves via network services like SSH and HTTP
- Found devices I’d forgotten about and checked what services they offered
- Realized the importance of securing open ports to prevent unauthorized access

**What this allowed me to do:**  
Understand my network’s layout and identify devices and services, which is essential for managing and securing any network.

---

## 🌐 Set Static IPs + Learned About Internal Networking
**What it is:** Static IP addressing involves assigning a fixed IP to devices instead of letting them get dynamic IPs via DHCP.

**How it works:** This keeps device IPs constant, which is important for servers or services that need reliable addressing.

**What I did:**
- Reserved IP addresses in pfSense’s DHCP server to assign static IPs by MAC address
- Configured static IPs directly on some devices like the Ubuntu server and Home Assistant VM
- Reviewed subnet masks and how they define the size and scope of the network
- Took notes on gateways and DNS settings for proper network routing

**What this allowed me to do:**  
Ensure stable and predictable network addressing, making device management and service access easier.

---

## 🏠 Messed Around with Home Assistant
**What it is:** Home Assistant is an open-source platform that lets you control and automate smart devices locally, without relying on cloud services.

**How it works:** It runs on a server or VM, connects to your IoT devices, and provides a dashboard and automation tools for managing them securely.

**What I did:**
- Installed Home Assistant OS in a Proxmox VM
- Assigned a static IP address via pfSense for easier access
- Explored the interface and added a few integrations (simulated devices since I’m just starting)
- Started learning about MQTT, a protocol commonly used for IoT device communication

**What this allowed me to do:**  
Explore IoT and smart home automation with better privacy and control, preparing for deeper projects in home networking.

---

## 🚀 Key Takeaways
- Doing hands-on work helps me grasp networking concepts better than just theory
- Setting up core tools like pfSense, Ubuntu, and Nmap demystified networking basics
- The tools I chose are powerful yet beginner-friendly, which is encouraging
- Running my own services locally gives me better control and privacy than cloud alternatives

---

## 📌 What’s Next (Week 2 Plans)
- Learn about VLANs to segment my network further
- Start using Docker containers to isolate services
- Set up Pi-hole for network-wide ad-blocking and DNS filtering

---
