# Networking Glossary – Lee Smyth 🧠

## Network Fundamentals

- **Network 🔌**  
  A group of connected devices (e.g., computers, phones, printers) that share resources like files, internet, or printers.

- **Internet 🌐**  
  A global network of networks connecting devices worldwide using standardized protocols like TCP/IP.

- **LAN (Local Area Network) 🖧**  
  A small network limited to a specific area, like a home, office, or campus.

- **WAN (Wide Area Network) 🛣️**  
  A large network spanning geographic areas, including the internet.

- **Packet 📦**  
  Small chunks of data sent over a network.

- **Latency ⌛**  
  The time it takes for a data packet to travel from source to destination, measured in milliseconds (ms). Lower is better.

- **Bandwidth 🚥**  
  The maximum amount of data that can be transferred in a given time, measured in Mbps or Gbps.

## Addressing

- **IP Address 📬**  
  A unique identifier for a device on a network.  
  - **IPv4**: 32-bit (e.g., `192.168.1.1`), ~4.3 billion addresses.  
  - **IPv6**: 128-bit (e.g., `2001:0db8::7334`), vastly more addresses.

- **Private IP Address 🏠**  
  IP addresses used within local networks, not routable on the internet.  
  - Examples: `192.168.x.x`, `10.x.x.x`, `172.16.0.0–172.31.255.255`.

- **Public IP Address 🌍**  
  Assigned by an ISP for internet access, shared via NAT for internal devices.

- **MAC Address 🧅**  
  A unique hardware identifier for a network device, e.g., `00:1A:2B:3C:4D:5E`. Used within a LAN and doesn’t change.

- **Port 🚪**  
  A numbered identifier for specific services or apps on a device.  
  - **Port 80**: HTTP (web traffic).  
  - **Port 443**: HTTPS (secure web).  
  - **Port 22**: SSH (remote login).  
  - **Port 53**: DNS (name lookup).

## Protocols

- **Protocol 📜**  
  Rules defining how data is sent and received (e.g., TCP/IP, HTTP).

- **TCP (Transmission Control Protocol) 📦**  
  A reliable, connection-oriented protocol ensuring data delivery in order.  
  - Used for: web browsing, file transfers.  
  - Slower but reliable.

- **UDP (User Datagram Protocol) ✈️**  
  A fast, connectionless protocol, less reliable as data may arrive out of order or get lost.  
  - Used for: video streaming, gaming, DNS.  
  - Faster but unreliable.

- **DHCP (Dynamic Host Configuration Protocol) 🧙‍♂️**  
  Automatically assigns IP addresses to devices on a network, eliminating manual configuration.

- **DNS (Domain Name System) 📖**  
  Translates domain names (e.g., google.com) into IP addresses (e.g., 8.8.8.8), like a phone book for the internet.

## Devices

- **Router 📶**  
  A device that connects a local network to the internet, routing data and often including a switch and wireless access point.

- **Switch 🔄**  
  A device that connects devices within a LAN, forwarding data only to the intended recipient, more efficient than a hub.

## Tools

- **Ping 🛰️**  
  A command that checks if a host is reachable and measures response time.

- **Traceroute / Tracert 🔍**  
  A tool showing the path (hops) data takes to a destination, useful for identifying delays or failures.

## Security and Configuration

- **Firewall 🚧**  
  A security system that controls incoming and outgoing network traffic based on rules, blocking or allowing specific ports, IPs, or protocols.

- **NAT (Network Address Translation) 🔁**  
  A router process that translates private IP addresses to a single public IP, allowing multiple devices to share one internet-facing IP.

- **Port Forwarding 🧭**  
  A router configuration that directs requests from a public IP and port to a private IP and port, used for hosting servers (e.g., games, websites).

## Frameworks

- **OSI Model (7 Layers) 🧱**  
  A framework for understanding network interactions.

| Layer | Name         | Description / Examples             |
|-------|--------------|------------------------------------|
| 7     | Application  | User interaction (HTTP, FTP, Email) |
| 6     | Presentation | Data formatting, encryption (SSL/TLS) |
| 5     | Session      | Session management (APIs, NetBIOS) |
| 4     | Transport    | Data transfer (TCP, UDP)           |
| 3     | Network      | Routing, addressing (IP, ICMP)     |
| 2     | Data Link    | MAC addressing, error detection (Ethernet) |
| 1     | Physical     | Hardware, cables, Wi-Fi signals    |

**Mnemonic**: "All People Seem To Need Data Processing."
