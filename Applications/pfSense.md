# 🛠️ pfSense Firewall & Router Setup

This documentation covers setting up pfSense as a virtual firewall/router within a Proxmox homelab. The setup creates a secure, segmented network by routing and managing traffic between the WAN (home network) and a private LAN subnet for lab devices.

## 📘 Glossary

- **pfSense:** Open-source firewall and router software based on FreeBSD.  
- **Proxmox:** A type-1 hypervisor platform for running VMs and containers.  
- **WAN:** Wide Area Network interface connecting to your external/home network.  
- **LAN:** Local Area Network interface serving your private homelab subnet.  
- **DHCP:** Protocol that assigns IP addresses automatically on a network.  
- **Bridge (vmbr0, vmbr1):** Linux network bridges in Proxmox connecting VMs to physical or virtual networks.

## 📦 Setup Specs

- **Platform:** Proxmox VE hypervisor  
- **VM Specs:**  
  - 2 vCPUs  
  - 2GB RAM  
  - 16GB Disk  
- **pfSense Version:** Latest stable release (e.g., 2.6.x)  
- **Network:**  
  - WAN connected to Proxmox bridge `vmbr0` (bridged to physical NIC)  
  - LAN connected to Proxmox bridge `vmbr1` (isolated internal bridge)  
- **Purpose:** Routing and firewalling between home network and private lab network; DHCP server for LAN clients

## ⚙️ Setup Steps

### 1. Created pfSense VM in Proxmox  
- Assigned two virtual NICs:  
  - `vtnet0` attached to `vmbr0` for WAN  
  - `vtnet1` attached to `vmbr1` for LAN  
- Installed pfSense using ISO image via Proxmox console.

### 2. Configured WAN Interface  
- Set WAN interface (`vtnet0`) to DHCP mode.  
- Confirmed WAN receives IP automatically from home router (e.g., `192.168.1.163`).  
- Verified WAN interface is up and reachable.

### 3. Configured LAN Interface  
- Assigned a static IPv4 address to LAN (`vtnet1`), e.g., `192.168.10.1/24`.  
- Enabled DHCP server on LAN with IP range (e.g., `192.168.10.100` to `192.168.10.200`) for clients.

### 4. Verified Connectivity  
- Created test VM/container bridged to `vmbr1` (LAN bridge).  
- Confirmed test client obtains DHCP IP in LAN subnet (e.g., `192.168.10.105`).  
- Verified test client can ping pfSense LAN IP (`192.168.10.1`).  
- Accessed pfSense Web UI from test client at `http://192.168.10.1`.

## 🔍 What This Setup Achieves

- Acts as a **middleman router/firewall** between your real home network (WAN) and private lab network (LAN).  
- Segments traffic for security and organization.  
- Provides DHCP service to automatically assign IPs on the lab LAN.  
- Enables hands-on practice with real-world routing, firewall, and network services.

## 🔧 Useful Commands & Checks

- View WAN interface IP on pfSense console:  
  ```sh
  ifconfig vtnet0
  ```

- View LAN interface IP on pfSense console:  
  ```sh
  ifconfig vtnet1
  ```

- Check test client IP and connectivity:  
  ```sh
  ip a
  ping 192.168.10.1
  ```

- Access pfSense Web UI from LAN client browser:  
  ```sh
  http://192.168.10.1
  ```

## 🚀 Next Steps

- Configure NAT and firewall rules for secure Internet access from LAN.  
- Explore VPN setup (e.g., WireGuard) on pfSense for secure remote access.  
- Add monitoring and logging services for network traffic analysis.  
- Experiment with VLANs and multi-segment networks.

This document will be updated as the pfSense homelab setup progresses.
