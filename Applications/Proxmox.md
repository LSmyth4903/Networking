# 🖥️ Proxmox

This document outlines the foundational setup of my homelab network environment. It includes Proxmox installation, virtual bridge creation, and network interface configuration. The goal is to emulate a realistic small-business network structure for CompTIA Network+ hands-on practice.

<img width="3839" height="1913" alt="image" src="https://github.com/user-attachments/assets/8ac976e5-389a-47a8-8daf-147d67c04514" />

---

## 📘 Glossary

- **Proxmox VE:** Open-source virtualization platform for running VMs and containers.  
- **Linux Bridge:** Virtual network switch allowing VMs and the host to communicate.  
- **Bridge Port:** A physical or virtual interface connected to a Linux bridge.  
- **WAN (Wide Area Network):** External network, typically your internet connection.  
- **LAN (Local Area Network):** Internal network where devices communicate locally.  
- **Static IP:** Fixed IP address assigned to a device or VM to ensure consistent network identity.  

---

## 🧱 Proxmox Installation

**Hardware Used:**

- Generic desktop hardware (e.g., Intel-based system)  
- 16GB RAM  
- 256GB SSD  

**Steps:**

1. Downloaded and flashed Proxmox VE ISO to USB.  
2. Installed Proxmox on bare metal.  
3. Accessed Proxmox web UI via `https://<proxmox-ip>:8006`.  

---

## 🌉 Network Bridge Configuration

Proxmox uses Linux bridges to allow virtual machines to communicate with the host network.

### Bridges Created:

| Bridge | Purpose | Physical NIC | Notes                                         |
| ------ | ------- | ------------ | --------------------------------------------- |
| vmbr0  | WAN     | enp1s0       | Connected to home router/internet             |
| vmbr1  | LAN     | None         | Internal virtual LAN (no physical NIC needed) |

### Configuration:

Configured via the Proxmox UI under **Datacenter > Node > Network**.

**vmbr0**:

- Connected to `enp1s0` (physical NIC)  
- `enp1s0` becomes a **bridge port** of `vmbr0`  
- Provides internet access to VMs via Proxmox's Linux bridging  

**vmbr1**:

- No physical NIC assigned  
- Acts as an **internal LAN bridge** for VM-to-VM communication  

---

## 🔧 Interface Naming Explanation

Linux uses **Predictable Network Interface Names** to consistently name interfaces based on hardware location:

- `enp1s0` means:  
  - `en` = Ethernet  
  - `p1` = PCI bus 1  
  - `s0` = Slot 0  

This differs from older `eno1` naming, which means onboard Ethernet 1. Your system uses `enp1s0` likely because the NIC is on a PCI bus, ensuring stable naming across reboots and hardware changes.

---

## 🚀 What This Allows Me To Do

- **Simulate real-world network environments** with clear WAN and LAN separation.  
- **Practice managing virtualization network interfaces** and Linux bridging.  
- **Test connectivity and troubleshooting tools** between VMs on different network segments.  
- **Build foundational virtualization and networking skills** recognized by recruiters.  
- **Extend my homelab network** by adding services like pfSense, VPNs, or IoT integrations.  
