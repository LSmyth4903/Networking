# 🛠️ Pi-hole Ad-Blocking DNS Sinkhole

This guide provides a comprehensive walkthrough for installing and configuring **Pi-hole** as a lightweight LXC container on a Proxmox homelab. Pi-hole serves as a **network-wide ad blocker** by filtering DNS queries, blocking ads, trackers, and malicious domains before they reach client devices. This documentation is designed to showcase system administration skills, including container management, network configuration, and DNS optimization.

<img width="1883" height="1093" alt="image" src="https://github.com/user-attachments/assets/214b488d-16a0-47d6-a38c-d68772d11d7b" />

## 📘 Glossary

- **Pi-hole**: Open-source software acting as a DNS sinkhole for network-wide ad blocking.
- **Proxmox**: Type-1 hypervisor platform for running virtual machines (VMs) and LXC containers.
- **DNS (Domain Name System)**: Protocol that translates domain names into IP addresses.
- **LXC Container**: Lightweight virtualized Linux environment in Proxmox.
- **Bridge (vmbr0)**: Proxmox network bridge connecting containers/VMs to the physical network.
- **Upstream DNS**: External DNS servers (e.g., Cloudflare, Google DNS) Pi-hole forwards queries to.

## 📦 Setup Specs

- **Platform**: Proxmox VE hypervisor
- **Container Specs**:
  - OS: Debian 11 (or Ubuntu 22.04)
  - 1 vCPU
  - 512–1024 MB RAM
  - 4–8 GB Disk
- **Pi-hole Version**: Latest stable release
- **Network**:
  - Bridged to `vmbr0` for LAN access
  - Static IP or DHCP reservation recommended
- **Purpose**:
  - DNS filtering for network-wide ad, tracker, and malware blocking
  - Centralized monitoring via web dashboard

## ⚙️ Setup Steps

### 1. Create LXC Container in Proxmox

1. **Download LXC Template**:
   - In Proxmox GUI, navigate to `Storage → local → Content → Templates`.
   - Download `debian-11-standard` or `ubuntu-22.04-standard`.

2. **Create Container**:
   - Hostname: `pihole`
   - Template: Debian 11 or Ubuntu 22.04
   - Set root password or SSH keys
   - Resources: 1 CPU, 512–1024 MB RAM, 4–8 GB disk
   - Network: Bridge to `vmbr0`, assign static IP or DHCP reservation
   - Start container and open console

### 2. Update System and Install Dependencies

```bash
apt update && apt upgrade -y
apt install curl -y
```

### 3. Install Pi-hole

```bash
curl -sSL https://install.pi-hole.net | bash
```

During setup:
- Select network interface (usually `eth0`).
- Choose upstream DNS provider (e.g., Cloudflare: `1.1.1.1`, Google: `8.8.8.8`).
- Accept default blocklists (customize later if needed).
- Enable web admin interface.
- Confirm static IP (set in Proxmox or during setup).
- Skip enabling Pi-hole DHCP unless replacing your router’s DHCP server.

### 4. Configure Network

- **Option 1 (Recommended)**: Set your router’s DNS server to the Pi-hole container’s IP.
- **Option 2**: Manually configure devices to use Pi-hole’s IP as their DNS server.

### 5. Access Pi-hole Admin Dashboard

- Open browser and navigate to: `http://<Pi-hole-IP>/admin`
- Log in with the password displayed at the end of Pi-hole installation.
- To change or reset the password:

```bash
pihole -a -p
```
*(Press Enter without input to disable the password.)*

## ⚙️ Managing Blocklists and Domains

### Adding Blocklists

1. Open Pi-hole admin dashboard: `http://<Pi-hole-IP>/admin`
2. Navigate to `Group Management → Adlists`.
3. Click `Add` and enter a blocklist URL (e.g., `https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts`).
4. Save and update gravity to fetch new lists:

```bash
pihole -g
```

### Whitelist Domains

- **Command Line**:

```bash
pihole -w example.com
```

- **Web UI**:
  - Go to `Whitelist`.
  - Add domains to allow.

### Blacklist Domains

- **Command Line**:

```bash
pihole -b badsite.com
```

- **Web UI**:
  - Go to `Blacklist`.
  - Add domains to block.

### Removing Domains from Lists

- Remove from whitelist:

```bash
pihole -w -d example.com
```

- Remove from blacklist:

```bash
pihole -b -d badsite.com
```

## 🔍 What This Setup Achieves

- Network-wide ad and tracker blocking
- Lightweight, containerized deployment on Proxmox
- Easy updates, backups, and restores via Proxmox
- Centralized monitoring without client-side software

## 🔧 Useful Commands

- Check Pi-hole status:

```bash
pihole status
```

- Update Pi-hole:

```bash
pihole -up
```

- Restart Pi-hole service:

```bash
sudo systemctl restart pihole-FTL
```

- Tail real-time DNS logs:

```bash
pihole -t
```

## 🛡️ Security Considerations

- **Restrict Admin Access**:
  - Secure the Pi-hole web interface by setting a strong password (`pihole -a -p`).
  - Consider limiting access to the admin dashboard to specific IP ranges using Proxmox firewall rules or an external firewall.

- **Network Isolation**:
  - Place the Pi-hole container in a dedicated VLAN to isolate it from other network traffic.
  - Use Proxmox’s network configuration to restrict container communication to DNS (port 53) and HTTP/HTTPS (ports 80/443) for the admin interface.

- **Regular Updates**:
  - Keep the container OS and Pi-hole updated to mitigate vulnerabilities (`apt update && apt upgrade -y`, `pihole -up`).
  - Monitor Pi-hole’s GitHub for security advisories.

- **Backup Strategy**:
  - Use Proxmox’s backup tools to snapshot the LXC container regularly.
  - Export Pi-hole settings via `pihole -a -t` (teleporter) for configuration backups.

## ⚡ Performance Optimization

- **Resource Allocation**:
  - Monitor CPU and RAM usage via Proxmox GUI. Increase to 2 vCPUs or 1–2 GB RAM if handling high DNS query volumes (e.g., >1000 queries/hour).
  - Use `htop` inside the container to check resource usage.

- **Blocklist Management**:
  - Avoid overloading Pi-hole with excessive blocklists, as this increases memory usage and query latency.
  - Regularly review blocklists for relevance and prune outdated ones (`pihole -g` to refresh).

- **Upstream DNS Optimization**:
  - Use fast, reliable upstream DNS providers like Cloudflare (`1.1.1.1`) or Quad9 (`9.9.9.9`) for low-latency responses.
  - Consider setting up Unbound as a local recursive DNS resolver for enhanced privacy and reduced external queries.

- **Caching**:
  - Enable Pi-hole’s DNS cache to reduce upstream queries. Adjust cache size in `/etc/pihole/pihole-FTL.conf` (e.g., `MAXDBDAYS=7` for longer retention).
  - Monitor cache hit rates in the Pi-hole dashboard to ensure efficiency.

## 🛠️ Troubleshooting Common Issues

- **DNS Resolution Fails**:
  - Verify the container’s network connectivity (`ping 8.8.8.8`).
  - Check Pi-hole’s status (`pihole status`) and ensure `pihole-FTL` is running.
  - Confirm the correct DNS server IP is set in your router or client devices.

- **Web Interface Inaccessible**:
  - Ensure the container’s IP is correct and reachable (`curl http://<Pi-hole-IP>/admin`).
  - Check if the lighttpd service is running: `sudo systemctl status lighttpd`.
  - Verify firewall rules allow HTTP traffic (port 80).

- **High Query Latency**:
  - Review upstream DNS provider performance in the Pi-hole dashboard.
  - Reduce blocklist size or optimize cache settings (see Performance Optimization).
  - Check for container resource constraints using Proxmox monitoring tools.

- **Blocked Legitimate Domains**:
  - Use the Pi-hole query log (`pihole -t`) to identify blocked domains.
  - Whitelist false positives (`pihole -w domain.com`) and test connectivity.

## 🚀 Next Steps

- Add custom blocklists for enhanced filtering.
- Integrate with Home Assistant for dashboard visualization.
- Set up Unbound for local DNS resolution and privacy.
- Enable Pi-hole’s DHCP server to manage IP addresses.
- Configure FTL metrics for detailed analytics.

## 📚 References

- [Pi-hole Official Documentation](https://docs.pi-hole.net/)
- [Pi-hole GitHub Repository](https://github.com/pi-hole/pi-hole)
- [Proxmox LXC Documentation](https://pve.proxmox.com/wiki/Linux_Container)
