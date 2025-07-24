# Network Implementation 🛠️

## Overview
This domain, 20% of the exam, focuses on deploying networks, including routing, switching, wireless, and physical setups. Study in small sections with hands-on labs using free tools.

## Routing Technologies 🌐
Manages data transfer between networks.

- **Static Routing**: Manually configured routes.
  - **Example**: Setting a route to a branch office.
  - **Details**: Configured with `ip route 192.168.2.0 255.255.255.0 10.0.0.1`. Simple but inflexible.
- **Dynamic Routing**:
  - **BGP**: Routes between autonomous systems.
    - **Example**: ISP routing internet traffic.
    - **Details**: Uses AS paths.
  - **EIGRP**: Cisco’s distance-vector protocol.
    - **Example**: Corporate network routing.
    - **Details**: Fast convergence, uses bandwidth/delay.
  - **OSPF**: Link-state protocol for large networks.
    - **Example**: Multi-office routing.
    - **Details**: Uses Dijkstra’s algorithm, supports areas.
- **Route Selection**: Chooses paths based on metrics.
  - **Example**: Preferring 1 Gbps over 100 Mbps.
  - **Details**: Uses cost or hop count.
- **NAT/PAT**: Translates private to public IPs.
  - **Example**: Home router sharing one public IP.
  - **Details**: PAT uses ports for multiple mappings.
- **FHRP**: Provides gateway redundancy (e.g., HSRP, VRRP).
  - **Example**: Router failover in a data center.
  - **Details**: Creates a virtual IP.
- **VIP**: Shared IP for redundancy or balancing.
  - **Example**: Directing traffic to available servers.
  - **Details**: Used in FHRP or load balancers.
- **Subinterfaces**: Virtual interfaces for VLAN routing.
  - **Example**: Routing VLAN 10 and 20 on one port.
  - **Details**: Configured as `interface g0/0.10`.

**Example**: A company uses OSPF for office routing and NAT for internet access.

**Homelab Activity**: **Configure Static and NAT**
- **Tool**: Cisco Packet Tracer.
- **Objective**: Set up static routing and NAT.
- **Steps**:
  1. Add two routers, one switch, and two PCs in Packet Tracer.
  2. Connect PC1 (192.168.1.2/24) to Router1, PC2 (192.168.2.2/24) to Router2.
  3. Configure Router1 (Gig0/0: 192.168.1.1/24, Gig0/1: 10.0.0.1/30) and Router2 (Gig0/0: 192.168.2.1/24, Gig0/1: 10.0.0.2/30).
  4. Add static route on Router1: `ip route 192.168.2.0 255.255.255.0 10.0.0.2`.
  5. Configure NAT on Router1: `access-list 1 permit 192.168.1.0 0.0.0.255`, `ip nat inside source list 1 interface Gig0/1 overload`.
  6. Ping from PC1 to PC2 to verify.
- **Why**: Practices routing and NAT for PBQs.[](https://www.howtonetwork.com/courses/comptia/comptia-network-n10-009/)

**Quiz**:
1. What’s static routing? (Answer: Manual route configuration)
2. What does NAT do? (Answer: Translates IPs)

**Graph**: Routing Protocol Complexity
```
   Static | Simple
   BGP    | Internet-scale
   EIGRP  | Cisco-specific
   OSPF   | Scalable
```

## Switching Technologies 🔌
Connects devices within a network.

- **VLANs**: Segments networks logically.
  - **Example**: Separating employee and guest Wi-Fi.
  - **Details**: Uses VLAN IDs (e.g., VLAN 10), configured with `vlan 10`.
- **Interface Configuration**: Sets port speed, duplex, or VLAN.
  - **Example**: Configuring 1 Gbps full-duplex.
  - **Details**: Uses `speed 1000`, `duplex full`.
- **Spanning Tree Protocol (STP)**: Prevents loops.
  - **Example**: Blocking redundant paths.
  - **Details**: Elects root bridge, blocks alternate paths.
- **MTU/Jumbo Frames**: Defines packet size.
  - **Example**: 9000-byte frames for video.
  - **Details**: Standard MTU is 1500 bytes.

**Example**: A switch uses VLANs for department separation and STP for loop prevention.

**Homelab Activity**: **Configure VLANs and STP**
- **Tool**: Cisco Packet Tracer.
- **Objective**: Set up VLANs and verify STP.
- **Steps**:
  1. Add two switches and four PCs in Packet Tracer.
  2. Create VLAN 10 and 20 on Switch1: `vlan 10`, `vlan 20`.
  3. Assign PC1 and PC2 to VLAN 10 (ports FastEthernet0/1, 0/2: `switchport access vlan 10`).
  4. Assign PC3 and PC4 to VLAN 20 (ports FastEthernet0/3, 0/4: `switchport access vlan 20`).
  5. Connect switches with a trunk link: `switchport mode trunk`.
  6. Verify STP with `show spanning-tree` (check root bridge).
  7. Ping within VLANs to confirm isolation.
- **Why**: Practices VLAN configuration and STP operation.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s a VLAN’s purpose? (Answer: Network segmentation)
2. Why use STP? (Answer: Prevent loops)

## Wireless Devices 📡
Enables wireless connectivity.

- **Channels/Frequencies**: Non-overlapping channels (e.g., 1, 6, 11 for 2.4 GHz).
  - **Example**: Setting channel 6 to avoid interference.
  - **Details**: 5 GHz has more channels, less interference.
- **SSID**: Network name.
  - **Example**: “OfficeWiFi” for an office.
  - **Details**: Can be hidden for security.
- **Network Types**:
  - **Infrastructure**: Devices connect via access points.
  - **Ad-hoc**: Device-to-device connections.
  - **Example**: Infrastructure for office Wi-Fi, ad-hoc for file sharing.
- **Encryption**:
  - **WPA2**: AES encryption.
  - **WPA3**: Enhanced security.
  - **Example**: WPA3 for a home network.
  - **Details**: WPA3 supports Opportunistic Wireless Encryption.
- **Guest Networks**: Isolates visitor devices.
  - **Example**: Guest Wi-Fi in a hotel.
  - **Details**: Uses VLANs or separate SSIDs.
- **Authentication**:
  - **PSK**: Password-based.
  - **802.1X**: Enterprise authentication with RADIUS.
  - **Example**: 802.1X for corporate Wi-Fi.
- **Antennas**:
  - **Omnidirectional**: Radiates in all directions.
  - **Directional**: Focused signal.
  - **Example**: Directional antenna for point-to-point.
- **Access Points (APs)**: Connects wireless to wired networks.
  - **Example**: Ceiling-mounted AP in an office.
  - **Details**: Supports multiple SSIDs, often uses PoE.

**Example**: An office AP uses channel 11, WPA3, and a guest network.

**Homelab Activity**: **Set Up a Wireless Network**
- **Tool**: Cisco Packet Tracer.
- **Objective**: Configure an AP with WPA3 and guest network.
- **Steps**:
  1. Add an AP, a switch, and two PCs in Packet Tracer.
  2. Connect AP to switch (FastEthernet0/1).
  3. Configure AP: SSID “MyWiFi,” channel 6, WPA3-PSK with password “Secure123.”
  4. Create a guest SSID “GuestWiFi” with password “Guest123.”
  5. Assign PC1 to MyWiFi, PC2 to GuestWiFi.
  6. Ping between PCs to test isolation (should fail if VLANs are used).
- **Why**: Simulates wireless configuration and security.[](https://www.howtonetwork.com/courses/comptia/comptia-network-n10-009/)

**Quiz**:
1. Name a 2.4 GHz non-overlapping channel. (Answer: 1, 6, or 11)
2. What’s WPA3? (Answer: Latest Wi-Fi encryption)

**Graph**: Wi-Fi Frequency Bands
```
   2.4 GHz | More range, more interference
   5 GHz   | Higher speed, less range
```

## Physical Installations ⚡️
Physical network infrastructure setup.

- **Wiring Distribution**:
  - **MDF**: Central wiring hub.
  - **IDF**: Connects to MDF.
  - **Example**: MDF in a data center, IDFs on office floors.
  - **Details**: Uses patch panels and structured cabling.
- **Power Considerations**:
  - **UPS**: Backup power.
  - **PDU**: Distributes power.
  - **Example**: UPS during outages.
  - **Details**: UPS offers battery backup, PDU manages power.
- **Environmental Factors**:
  - **Temperature**: 20–25°C for equipment.
  - **Humidity**: 40–60% to prevent corrosion.
  - **Example**: Cooling in a server room.
  - **Details**: HVAC ensures optimal conditions.

**Example**: A data center uses an MDF, UPS, and HVAC for reliability.

**Homelab Activity**: **Simulate MDF/IDF Setup**
- **Tool**: Cisco Packet Tracer.
- **Objective**: Design an MDF/IDF wiring layout.
- **Steps**:
  1. Add one switch (MDF), two switches (IDFs), and four PCs.
  2. Connect IDF1 and IDF2 to MDF via Ethernet (trunk links).
  3. Assign PC1 and PC2 to IDF1 (VLAN 10), PC3 and PC4 to IDF2 (VLAN 20).
  4. Configure trunk ports on MDF: `switchport mode trunk`.
  5. Verify connectivity with `ping` and `show vlan brief`.
- **Why**: Simulates structured cabling and VLAN distribution.[](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)

**Quiz**:
1. What’s an MDF? (Answer: Main wiring hub)
2. Why control temperature? (Answer: Prevent equipment damage)
