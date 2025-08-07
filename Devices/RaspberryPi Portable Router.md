# Raspberry Pi Portable Router with OpenWrt

## Why I Built This

As I’ve been learning about security and networking, I quickly realized how risky public WiFi networks in places like coffee shops can be. These networks usually lack proper security, making it easy for attackers to intercept your data or compromise your devices.

That’s what pushed me to take control of my online safety by building a portable and secure private network. Now, with this Raspberry Pi-powered router, I can connect my devices through my own trusted WiFi hotspot, keeping my data safe no matter where I go.

As a bonus, I integrated OpenVPN into the setup. This lets me connect back to my home network securely from anywhere in the world. I can access services on my LAN as if I were at home, all through a private, encrypted tunnel.

---

## Overview

This project documents the creation of a portable router using a Raspberry Pi 4B (4GB) running OpenWrt, a lightweight, powerful router operating system.

I followed this NetworkChuck tutorial to guide the setup:  
🔗 YouTube: **Portable OpenWrt Router on Raspberry Pi 4B**

The end result is a compact, secure, and highly customizable router that I can carry in my bag and use whenever I'm on the move.

---

## Hardware Used

- Raspberry Pi 4 Model B (4GB RAM)  
- MicroSD card (16GB+ recommended, Class 10)  
- MicroSD card reader  
- Ethernet cable  
- HDMI to Mini-HDMI cable (optional for first boot)  
- USB WiFi adapter or secondary Ethernet adapter (for dual interfaces)  
- Travel-friendly case (optional but recommended)  
- Portable power supply (e.g. battery bank or USB-C PD)

![All parts used in this build](https://github.com/user-attachments/assets/6be81a73-3fe0-4052-ad29-cf5df8169c8b)

---

## Software

- OpenWrt (official or custom build for Raspberry Pi 4)  
- SSH for headless configuration  
- OpenVPN (optional but recommended for secure remote access)

---

## Setup Process

### 1. Download and Flash OpenWrt

Visit the OpenWrt Raspberry Pi download page, download the correct image for the Raspberry Pi 4, and flash it to your MicroSD card using a tool like balenaEtcher.

![Flashing OpenWrt using Etcher](https://github.com/user-attachments/assets/6628e081-257c-4165-b49a-a01d399fb40c)

---

### 2. First Boot

Insert the MicroSD card into the Raspberry Pi.  
Power it on using USB-C (from a wall adapter or power bank).  
Connect it via Ethernet to your PC or your local network.

---

### 3. Find Pi’s IP Address

Use your router’s web UI to find the new device.  
Look for a hostname like “OpenWrt” or a new IP address in the DHCP client list.

---

### 4. Access OpenWrt via SSH

SSH into the Pi using the IP address (e.g., `ssh root@192.168.1.1`).  
No password is set by default, but you’ll set one in the next step.
<img width="557" height="250" alt="image" src="https://github.com/user-attachments/assets/b6c363fa-e429-4fbc-ba33-10942212e8d4" />


---

### 5. Set Root Password

Run the following command to set a secure root password:

```bash
passwd
```

This is critical for securing your device.

---

### 6. Configure Network Interfaces

Edit the network configuration file located at `/etc/config/network` using a text editor like `vi` or `nano`. Following NetworkChuck’s tutorial, configure the LAN and WAN interfaces:

- **LAN**: For your private network (devices connecting to the Pi).  
- **WAN**: For the public internet source (via WiFi adapter or Ethernet).

Example `/etc/config/network`:

```bash
config interface 'lan'
    option proto 'dhcp'
    option ifname 'eth0'
    option hostname 'OpenWrt'

config interface 'wan'
    option proto 'dhcp'
    option ifname 'wlan0'
```

Save the file and apply changes:

```bash
uci commit network
/etc/init.d/network restart
```

---

### 7. Setup Wireless

Edit the wireless configuration file at `/etc/config/wireless` to enable the WiFi radio and create a secure SSID.

Example `/etc/config/wireless`:

```bash
config wifi-device 'radio0'
    option disabled '0'
    option channel '1'
    option band '2g'

config wifi-iface 'default_radio0'
    option device 'radio0'
    option mode 'ap'
    option ssid 'MyPortableWiFi'
    option encryption 'psk2'
    option key 'YourSecurePassword'
    option network 'lan'
```

Save and apply changes:

```bash
uci commit wireless
wifi reload
```

This creates a secure WiFi hotspot with WPA2 encryption.

---

### 8. Install Additional Packages (Optional)

Update the package list and install additional tools like OpenVPN if needed:

```bash
opkg update
opkg install luci-app-openvpn
```

---

### 9. Setup OpenVPN (Optional)

Edit the OpenVPN configuration file at `/etc/config/openvpn` to set up a client or server for secure remote access to your home network.

Example `/etc/config/openvpn`:

```bash
config openvpn 'my_vpn'
    option enabled '1'
    option client '1'
    option dev 'tun'
    option proto 'udp'
    option remote 'your.vpn.server.ip 1194'
    option ca '/etc/openvpn/ca.crt'
    option cert '/etc/openvpn/client.crt'
    option key '/etc/openvpn/client.key'
```

Save, then restart OpenVPN:

```bash
uci commit openvpn
/etc/init.d/openvpn restart
```

Upload necessary certificate files (`ca.crt`, `client.crt`, `client.key`) via SCP or LuCI.

---

## What This Project Enables

This small device packs a punch. Here’s what I can now do:

- **Create a Secure Hotspot Anywhere**: No more using risky public WiFi. I connect through my Pi’s secure WiFi hotspot.  
- **Extend and Share Internet Connections**: Turn any Ethernet or WiFi source into a personal network for multiple devices.  
- **Connect Back Home with VPN**: Access Home Assistant, local files, and services just like I’m at home.  
- **Portable and USB-Powered**: Compact and powered by any USB-C battery bank.  
- **Educational Tool**: Learned tons about networking, SSH, and router config.  

---

## Future Improvements

- Add internal battery with UPS HAT  
- Add OLED screen for IP and status  
- Auto-connect to known WiFi hotspots as WAN  
- Integrate WireGuard for faster VPN tunnels  
- Custom enclosure with cable management  

---

## References

- 🔗 YouTube: [NetworkChuck Portable OpenWrt Router Guide]  
- 📄 OpenWrt Raspberry Pi Docs
