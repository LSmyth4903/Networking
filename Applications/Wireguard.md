# 🔒 WireGuard VPN Setup – Proxmox Homelab

This tutorial covers setting up WireGuard on a Proxmox server to create a secure VPN tunnel for protecting the homelab network and enabling remote access to services like Home Assistant and GitHub workflows.

---

## 📘 Glossary

- **WireGuard:** A fast, modern VPN protocol for secure network tunnels.
- **Proxmox:** A type-1 hypervisor for managing virtual machines and containers.
- **Peer:** A device (e.g., phone or laptop) connecting to the VPN.
- **wg0:** The default WireGuard network interface name.
- **Private/Public Key Pair:** Cryptographic keys for secure communication (private key is secret, public key is shared).

---

## 📦 Setup Specs

- **Platform:** Proxmox virtual machine  
- **VM Specs:**
  - 2 vCPUs  
  - 2GB RAM  
  - 32GB Disk  
- **OS:** Debian 12  
- **Network:** Static IP assigned via pfSense on LAN subnet  
- **Purpose:** Secure remote access to homelab services (e.g., Home Assistant) and GitHub

---

## ⚙️ Installation Steps

**Overview:** The following steps guide you through setting up a Debian VM on Proxmox, installing and configuring WireGuard, enabling network forwarding, setting up firewall rules, configuring a client device, and testing connectivity to ensure secure access to Home Assistant and GitHub.

1. **Created a Debian VM in Proxmox**
   - Used Proxmox web interface to create a VM with 2 vCPUs, 2GB RAM, and 32GB disk. Installed Debian 12 from an ISO image.

2. **Updated the System**
   - Logged into the VM via SSH or Proxmox console and ran:
     ```bash
     apt update && apt upgrade -y
     ```

3. **Installed WireGuard**
   - Installed WireGuard and tools:
     ```bash
     apt install wireguard wireguard-tools -y
     ```

4. **Generated Key Pairs**
   - Created private and public keys for the server:
     ```bash
     wg genkey | tee /etc/wireguard/privatekey | wg pubkey > /etc/wireguard/publickey
     ```

5. **Configured the WireGuard Server**
   - Created `/etc/wireguard/wg0.conf`:
     ```ini
     [Interface]
     PrivateKey = <server-private-key>
     Address = 10.0.0.1/24
     ListenPort = 51820
     PostUp = iptables -A FORWARD -i wg0 -j ACCEPT; iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
     PostDown = iptables -D FORWARD -i wg0 -j ACCEPT; iptables -t nat -D POSTROUTING -o eth0 -j MASQUERADE

     [Peer]
     PublicKey = <client-public-key>
     AllowedIPs = 10.0.0.2/32
     ```
   - Replaced `<server-private-key>` and `<client-public-key>` with actual keys.

6. **Enabled IP Forwarding**
   - Edited `/etc/sysctl.conf` to add:
     ```bash
     echo "net.ipv4.ip_forward=1" >> /etc/sysctl.conf
     sysctl -p
     ```

7. **Started WireGuard**
   - Enabled and started the WireGuard service:
     ```bash
     systemctl enable wg-quick@wg0
     systemctl start wg-quick@wg0
     ```

8. **Configured pfSense Firewall**
   - Added a firewall rule in pfSense to allow UDP traffic on port 51820 to the WireGuard VM’s static IP.

9. **Set Up Client Configuration**
   - Generated client key pairs on a client device (e.g., laptop):
     ```bash
     wg genkey | tee privatekey | wg pubkey > publickey
     ```
   - Created a client configuration file (e.g., `wg0-client.conf`):
     ```ini
     [Interface]
     PrivateKey = <client-private-key>
     Address = 10.0.0.2/24

     [Peer]
     PublicKey = <server-public-key>
     Endpoint = <proxmox-static-ip>:51820
     AllowedIPs = 0.0.0.0/0
     ```
   - Used this with a WireGuard client (e.g., WireGuard app on mobile or desktop).

10. **Tested Connectivity**
    - Activated the client VPN and verified connectivity:
      ```bash
      ping 10.0.0.1
      ```
    - Confirmed access to Home Assistant (http://<ha-static-ip>:8123) and GitHub via SSH over the VPN.

---

## 🖼️ Current Setup Overview

- **Server:** WireGuard running on a Debian VM in Proxmox.
- **Clients:** Configured for laptop and phone for secure homelab access.
- **Services Accessed:** Home Assistant for monitoring/control, GitHub for secure repository operations.

---

## 🔍 Features Explored

- Secure VPN tunnel for remote homelab access  
- Static IP setup via pfSense  
- Key-based authentication for peers  
- Remote access to Home Assistant’s web UI  
- Secure SSH-based GitHub repository access  
- Low resource usage on Proxmox

---

## 🤔 Why WireGuard

- Encrypts all homelab traffic  
- Enables secure remote access to Home Assistant and other services  
- Lightweight and faster than OpenVPN  
- Uses modern cryptography for strong security  
- Supports secure GitHub interactions privately  
- Scalable for additional clients/services

---

## 🧠 What This Enables

- Secure remote access to Proxmox and Home Assistant  
- Encrypted homelab traffic  
- Private GitHub operations (e.g., git clone, push)  
- VPN and firewall rule experimentation  
- Foundation for adding more services securely  
- Full control over network traffic without third-party VPNs

---

📌 *This file will be updated as the setup is refined or expanded.*
