# Networking Day 1: Fundamentals

📅 Date: 7 July 2025  
👤 Name: Lee Smyth

---

## Topics Explored
- IP addressing (private vs public)
- NAT (Network Address Translation)
- Ports and their role in networking
- Ping and traceroute commands
- Basic network diagnostics
- How home networks communicate with the internet

---

## 🔧 Practical Lab Activity

### Step 1: Checked Local Network Info 
command `ipconfig`
- IPv4 Address: `192.168.x.x`
- Default Gateway: `192.168.x.1`
- DNS Server: `192.168.x.x`

### Step 2: Pinged the Gateway
- Command: `ping 192.168.x.1`
- Result: Success ✅

### Step 3: Traced Route to Reddit
- Command: `tracert reddit.com`
- Hops: 7  
- Final IP: `151.101.129.140`  
- One timeout at hop 4 (expected)

### Step 4: Disconnect from Internet and Retest with google.com
- IP remained private
- Ping to `8.8.8.8` failed (no internet)
- Confirmed router is needed for NAT

---

## 🌐 Key Concepts Learned

### Private IP Addresses
- Used within local home networks only (`192.168.x.x`)
- Large corporations use IP addresses starting in (`10.0.0.0/8`)
- Cannot access internet directly
- Requires NAT to make it public

### NAT
- Router rewrites private IP to public IP
- Shares one public IP across multiple devices

### Ports
- Allow apps and services to run on the same device
- If the IP address is the house number, this is room number identifying each device
- Example: Port 443 for secure web traffic (HTTPS), Port 80 for standard web traffic, Port  22 used for SSH, Port 53 used for DNS

### Traceroute
- Visual path of how a packet reaches a destination
- Useful for identifying where delays or failures happen

---

## 💡 Reflections
- Interesting to see actual routing to Reddit
- NAT and port rewriting make much more sense now
- How Ip addresses are assigned within a home network make sense with 192 being reserved for home networks and 10 being reserved for private networks such as corportaions.
---

## 🎯 Next Steps
- Use Wireshark to inspect packets
- Try port forwarding and run a local web server
- Simulate networks in Cisco Packet Tracer

